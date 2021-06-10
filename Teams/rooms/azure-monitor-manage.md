---
title: Gestire Microsoft Teams Rooms dispositivi con Monitor di Azure
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
description: Questo articolo spiega come gestire i dispositivi Microsoft Teams Rooms in modo integrato con Monitor di Azure.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41375c313940099b6ed6e102e2452290e0817bec
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2021
ms.locfileid: "50874766"
---
# <a name="manage-microsoft-teams-rooms-devices-with-azure-monitor"></a>Gestire Microsoft Teams Rooms dispositivi con Monitor di Azure

Questo articolo spiega come gestire i dispositivi Microsoft Teams Rooms in modo integrato con Monitor di Azure.

È possibile configurare Monitoraggio di Azure in modo da fornire telemetria di base che consente di gestire Microsoft Teams delle sale riunioni. Per [informazioni dettagliate, vedere Pianificare](azure-monitor-plan.md) Microsoft Teams Rooms gestione delle Microsoft Teams Rooms con Azure [Monitor.](azure-monitor-deploy.md) Con il maturare della soluzione di gestione, è possibile usare altre funzionalità di gestione e dati per creare una visualizzazione più dettagliata delle prestazioni dei dispositivi.

## <a name="understand-the-log-entries"></a>Comprendere le voci del log

Le descrizioni degli eventi seguenti vengono inserite nel campo di descrizione del log eventi ogni cinque minuti, quando l'app Microsoft Teams Rooms registra le informazioni corrispondenti nel log Windows eventi. Il Microsoft Monitoring Agent passa questi record a Log Analytics in Monitoraggio di Azure, che li analizza nel dashboard creato in Distribuire la gestione Microsoft Teams Rooms con [Monitoraggio di Azure.](azure-monitor-deploy.md) Con il dashboard è possibile esaminare le singole voci del log per determinare i corsi di azione, se necessario.

Gli ID evento 2000 e 3000 indicano che il dispositivo in questione funziona come previsto. Gli ID evento 2001 e 3001 indicano che è stato rilevato un problema. L'ID evento 4000 può richiedere un intervento se visualizzato più spesso del previsto, rispetto a una previsione impostata o ad altri dispositivi distribuiti nell'organizzazione.

La comprensione di queste descrizioni degli eventi segnala rapidamente i problemi e fornisce un punto di partenza per ulteriori procedure di risoluzione dei problemi.

| Livello &nbsp; ID &nbsp; evento|Comportamento &nbsp; dell'evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Descrizione &nbsp; dell'evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> Informazioni | Si tratta di un evento heartbeat integro. Ogni 5 minuti, Microsoft Teams Rooms verifica che sia connesso a Microsoft Teams o Skype for Business e che abbia connettività Exchange rete. <br> Se tutti e 3 i fattori sono veri, scrive l'ID evento 2000 nel log eventi ogni 5 minuti finché il dispositivo non è offline o una o più condizioni non vengono più soddisfatte. | `{"Description":"Heartbeat is healthy.", "ResourceState":"Healthy", "OperationName":"Heartbeat", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com",  "DisplayName":"Display name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10",  "IPv6Address":"IP v6 address"}` <br><br> In questo esempio sono state soddisfatte tutte le condizioni di heartbeat e il Microsoft Teams Rooms dispositivo è stato contrassegnato come integro. In caso di errori, l'app registrerebbe invece l'ID evento 2001. |
| 2001  <br> Errore | Si tratta di un evento di errore dell'app. Ogni 5 minuti, Microsoft Teams Rooms verifica che sia stato eseguito l'accesso a Microsoft Teams o Skype for Business con connettività di rete Exchange rete. Se uno o più fattori non sono veri, scrive EventID 2001 nel log eventi ogni 5 minuti finché il dispositivo non è offline o non vengono soddisfatte di nuovo tutte le condizioni.  | `{"Description":"Network status : Healthy. Exchange status : Connected. Signin status: Unhealthy. ", "ResourceState":"Unhealthy", "OperationName":"Heartbeat", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br>  In questo esempio, Microsoft Teams Rooms che la connessione di rete era integra e che l'app era connessa a Exchange, ma la parte in grassetto indica che l'app non è connessa. Potrebbe trattarsi di un problema di configurazione nel dispositivo o nell'host.  <br> <br> Lo stato rete viene visualizzato come Integro o Non integro. Se lo stato non è integro, è possibile che si sia verificato un problema di rete o che il dispositivo sia stato scollegato (ma probabilmente si potrebbero verificare anche errori di Exchange e Microsoft Teams o Skype for Business).  <br><br> Lo Exchange stato viene visualizzato come Connesso o come uno dei seguenti: Disconnesso, Connessione, AutodiscoveryError (l'errore più comunemente visualizzato), GeneralError o ServerVersionNotSupported. Se lo stato è Connessione, attendere finché non viene inviato il messaggio di integrità successivo, perché altri errori rimandano il problema a un amministratore con esperienza nella risoluzione Exchange problemi.  <br><br>  Lo _stato di accesso_ (che indica che l'app è stata con accesso) viene visualizzato come Integro o Non _integro._  Se lo stato non è integro, inviare un tecnico per ulteriori indagini. |
| 3000  <br> Informazioni | Questo evento verifica che un controllo hardware sia stato eseguito e che sia stato trovato integro. Ogni 5 minuti Microsoft Teams Rooms che i componenti hardware configurati, ad esempio lo schermo anteriore della sala, il microfono, l'altoparlante e la fotocamera, siano collegati e funzionanti. Se tutti i componenti sono integri, scrive EventID 3000 nel log eventi. Questo evento viene scritto ogni 5 minuti, a meno che non si sia verificato un problema con un dispositivo connesso.  <br> | `{"Description":"HardwareCheckEngine is healthy.",  "ResourceState":"Healthy", "OperationName":"HardwareCheckEngine",  "OperationResult":"Pass", "OS":"Windows 10",  "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0",  "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> In questo esempio sono stati superati tutti i controlli hardware. In caso di errori, l'app registrerebbe invece l'ID evento 3001. |
| 3001  <br> Evento di errore  | Si tratta di un evento di errore hardware. L Microsoft Teams Rooms app include un processo che controlla l'integrità dei componenti hardware connessi (davanti alla sala, al microfono, all'altoparlante, alla fotocamera) ogni 5 minuti. Se uno o più componenti non sono integri, scrive EventID 3001 nel log eventi. Questo evento viene scritto ogni 5 minuti finché il problema con il dispositivo non viene risolto.   | `{"Description":" Front of Room Display status : Unhealthy. Configured display count is 2. Real display count is 0. Conference Microphone status : Unhealthy. Conference Speaker status : Healthy. Default Speaker status : Healthy. Camera status : Healthy.", "ResourceState":"Unhealthy", "OperationName":"HardwareCheckEngine", "OperationResult":"Fail", "OS":"Windows 10", "OSVersion":"10.0.14393.1198", "Alias":"alias<span></span>@contoso.com", "DisplayName":"Yosemite conference room", "AppVersion":"2.0.58.0", "IPv4Address":"10.10.10.10", "IPv6Address":"IPv6Address", "IPv4Address2":"10.10.10.10"}` <br><br>  Le periferiche hardware sono visualizzate come integre o non integre. <br> In questo esempio sono configurati due _schermi davanti_ alla sala e attualmente nessuno dei due è disponibile. Lo _stato del microfono della_ conferenza non è _integro,_ che può avere diverse cause possibili. Poiché almeno una risorsa non ha superato il controllo, ResourceState è elencato come Non integro. Inviare un tecnico per ulteriori indagini. |
| 4000  <br> Informazioni  <br> | Si tratta di un evento riavvio dell'app. Ogni volta che l'app viene riavviata, l'evento viene inserito nel Windows eventi.  <br> | `{"Description":"App restarts.", "ResourceState":"Healthy", "OperationName":"Restart", "OperationResult":"Pass", "OS":"Windows 10", "OSVersion":"10.0.14393.693", "Alias":"alias<span></span>@domain.com", "DisplayName":"Display Name", "AppVersion":"1.0.38.0", "IPv4Address":"10.10.10.10", "IPv6Address":"ip v6 address"}` <br><br> L'app può essere riavviata per vari motivi. Confrontare la frequenza di riavvio dei dispositivi nello stesso edificio e in edifici diversi. Tenere presente i problemi noti, ad esempio le fluttuazioni e gli errori di alimentazione, in quanto possono fornire indicazioni sui problemi dell'infrastruttura.|

## <a name="related-topics"></a>Argomenti correlati
 

[Pianificare Microsoft Teams Rooms gestione con Monitor di Azure](azure-monitor-plan.md)

[Distribuire Microsoft Teams Rooms gestione dei dati con Monitor di Azure](azure-monitor-deploy.md)
