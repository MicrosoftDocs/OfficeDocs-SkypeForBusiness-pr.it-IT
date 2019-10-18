---
title: Gestire i dispositivi Microsoft teams Rooms con Azure monitor
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.assetid: f8109905-3279-475f-a64b-31d37af48bfe
ms.collection:
- M365-collaboration
description: Questo articolo illustra come gestire i dispositivi Microsoft teams rooms in modo integrato con Azure monitor.
ms.openlocfilehash: 33132d7d72498fd01a156ce28114d1e584d6760c
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569930"
---
# <a name="manage-microsoft-teams-rooms-devices-with-azure-monitor"></a>Gestire i dispositivi Microsoft teams Rooms con Azure monitor

Questo articolo illustra come gestire i dispositivi Microsoft teams rooms in modo integrato con Azure monitor.

Puoi configurare Azure monitor in grado di fornire la telemetria di base per gestire i dispositivi Skype meeting room. Per informazioni dettagliate, vedere [pianificare la gestione di Microsoft teams Rooms con Azure monitor](azure-monitor-plan.md) e [distribuire Microsoft teams Management Rooms con Azure monitor](azure-monitor-deploy.md) . Man mano che la tua soluzione di gestione è matura, puoi usare funzionalità di gestione e dati aggiuntive per creare una visualizzazione più dettagliata delle prestazioni del dispositivo.

## <a name="understand-the-log-entries"></a>Informazioni sulle voci di log

Le descrizioni degli eventi seguenti vengono inserite nel campo Descrizione log eventi ogni cinque minuti, quando l'app Microsoft teams Rooms registra le informazioni corrispondenti nel registro eventi di Windows. L'agente di monitoraggio Microsoft passa questi record per registrare analisi in Azure monitor, che li analizza nel dashboard creato in distribuzione di [Microsoft teams Rooms Management con Azure monitor](azure-monitor-deploy.md). Con il dashboard, è possibile esaminare le singole voci di log per determinare i corsi di azione, se necessario.

Gli ID evento 2000 e 3000 indicano che il dispositivo in questione funziona come previsto. Gli ID evento 2001 e 3001 indicano che è stato trovato un problema. L'ID evento 4000 può richiedere un'azione se viene visualizzato più spesso di quanto previsto, rispetto a una previsione impostata o ad altri dispositivi distribuiti nell'organizzazione.

La comprensione di queste descrizioni degli eventi avvisa rapidamente i problemi e fornisce un punto di partenza per ulteriori problemi.

| Livello&nbsp;ID&nbsp;evento|Comportamento&nbsp;dell'evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Descrizione&nbsp;dell'evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|
|:---    |:---   |:---  |
| 2000  <br> Informazioni | Si tratta di un evento di heartbeat corretto. Ogni 5 minuti, Microsoft teams Rooms verifica che sia connesso a Microsoft teams o Skype for business e disponga della connettività di rete e di Exchange. <br> Se tutti e tre i fattori sono veri, scrive l'ID evento 2000 nel log eventi ogni 5 minuti finché il dispositivo non è offline o una o più delle condizioni non sono più soddisfatte. | {"Descrizione": "heartbeat è integro.", "ResourceState": "integro", "OperationName": "heartbeat", "OperationResult": "Pass", "OS": "Windows 10", "OSVersion": "10.0.14393.693", "alias":<span></span>"alias @contoso. com", "DisplayName": "nome visualizzato "," AppVersion ":" 1.0.38.0 "," Indirizzoipv4 ":" 10.10.10.10 "," Indirizzoipv6 ":" indirizzo IP V6 "} <br><br> In questo esempio tutte le condizioni di heartbeat sono state soddisfatte e il dispositivo Microsoft teams Rooms è stato contrassegnato come integro. In caso di errori, l'app registrerà invece l'ID evento 2001. |
| 2001  <br> Errore | Si tratta di un evento di errore dell'app. Ogni 5 minuti, Microsoft teams Rooms verifica che sia connesso a Microsoft teams o Skype for business con la connettività di rete e Exchange. Se uno o più fattori non sono veri, scrive EventId 2001 nel log eventi ogni 5 minuti fino a quando il dispositivo non è in linea o tutte le condizioni vengono soddisfatte ancora una volta.  | {"Descrizione": "stato rete: integro. Stato Exchange: connesso. **Stato di accesso: non sano.** "," ResourceState ":" non sano "," OperationName ":" heartbeat "," OperationResult ":" fail "," OS ":" Windows 10 "," OSVersion ":" 10.0.14393.693 "," alias ":" "," DisplayName "," nome visualizzato "," AppVersion ":" 1.0.38.0 "," Indirizzoipv4 ":" 10.10.10.10 "," Indirizzoipv6 ":" indirizzo IP V6 "} <br><br>  In questo esempio, Microsoft teams Rooms ha stabilito che la connessione di rete è stata corretta e che l'app è stata connessa a Exchange, ma la parte in grassetto indica che l'app non è connessa. Potrebbe trattarsi di un problema di configurazione nel dispositivo o nell'host.  <br> <br> Lo stato della rete viene visualizzato come integro o non integro. Se lo stato è non sano, è possibile che si verifichi un problema di rete oppure che il dispositivo sia stato scollegato, ma che si disponga probabilmente anche di errori di Exchange e Microsoft teams o Skype for business.  <br><br> Lo stato di Exchange viene visualizzato come connesso o una delle opzioni seguenti: disconnected, Connecting, AutodiscoveryError (l'errore più comune), GeneralError o ServerVersionNotSupported. Se lo stato si connette, attendere che venga inviato il messaggio di integrità successivo, in caso di altri errori, fare in modo che un amministratore abbia esperienza nella risoluzione dei problemi di Exchange.  <br><br>  Lo stato di accesso (che indica che l'app è connesso) viene visualizzato come integro o non integro. Se lo stato è non sano, inviare un tecnico per approfondire l'analisi. |
| 3000  <br> Informazioni | Questo evento verifica che sia stato eseguito un controllo hardware e sia stato ritenuto integro. Ogni 5 minuti Microsoft teams Rooms controlla che i componenti hardware configurati, ad esempio il fronte della visualizzazione della sala, il microfono, l'altoparlante e la fotocamera, siano connessi e funzionanti. Se tutti i componenti sono integri, scrive EventId 3000 nel log eventi. Questo evento viene scritto ogni 5 minuti a meno che non si sia verificato un problema con un dispositivo connesso.  <br> | {"Description": "HardwareCheckEngine è integro.", "ResourceState": "Healthy", "OperationName": "HardwareCheckEngine", "OperationResult": "Pass", "OS": "Windows 10", "OSVersion": "10.0.14393.693", "alias": "<span></span>alias @contoso. com", " DisplayName ":" nome visualizzato "," AppVersion ":" 1.0.38.0 "," Indirizzoipv4 ":" 10.10.10.10 "," Indirizzoipv6 ":" IP V6 Address "}  <br><br> In questo esempio sono stati passati tutti i controlli hardware. In caso di errori, l'app registrerà invece l'ID evento 3001. |
| 3001  <br> Evento di errore  | Si tratta di un evento di errore hardware. L'app Microsoft teams Rooms ha un processo che controlla l'integrità dei componenti hardware connessi (prima della sala, del microfono, del relatore, della videocamera) ogni 5 minuti. Se uno o più componenti non sono sani, scrive EventId 3001 nel log eventi. Questo evento viene scritto ogni 5 minuti finché non viene risolto il problema con il dispositivo.   | {"Descrizione": " **stato di visualizzazione della sala: non sano.** Il numero di visualizzazioni configurato è 2. Il numero di visualizzazione reale è 0. **Stato microfono conferenza: non sano.** Stato altoparlante conferenza: integro. Stato altoparlante predefinito: integro. Stato fotocamera: integro. "," ResourceState ":" non integro "," OperationName ":" HardwareCheckEngine "," OperationResult ":" fail "," OS ":" Windows 10 "," OSVersion ":" 10.0.14393.1198 "," alias ":"<span></span>alias @contoso. com "," DisplayName ":" Yosemite sala riunioni "," AppVersion ":" 2.0.58.0 "," Indirizzoipv4 ":" 10.10.10.10 "," Indirizzoipv6 ":" Indirizzoipv6 "," IPv4Address2 ":" 10.10.10.10 "} <br><br>  Le periferiche hardware vengono visualizzate in modo sano o non integro. <br> In questo esempio sono configurati due fronti di visualizzazione della sala e attualmente nessuno di essi è disponibile. Lo stato del microfono conferenza non è sano, che potrebbe avere diverse possibili cause. Poiché almeno una risorsa non ha superato il controllo, il ResourceState viene elencato come non sano. Inviare un tecnico per indagare ulteriormente. |
| 4000  <br> Informazioni  <br> | Si tratta di un evento di riavvio dell'app. Ogni volta che l'app viene riavviata, l'evento verrà loggato nel log eventi di Windows.  <br> | {"Description": "riavvia app.", "ResourceState": "Healthy", "OperationName": "Restart", "OperationResult": "Pass", "OS": "Windows 10", "OSVersion": "10.0.14393.693", "alias": "alias<span></span>@domain. com", "DisplayName": "nome visualizzato", " AppVersion ":" 1.0.38.0 "," Indirizzoipv4 ":" 10.10.10.10 "," Indirizzoipv6 ":" indirizzo IP V6 "} <br><br> L'app può essere riavviata per diversi motivi. Confrontare la frequenza di riavvio dei dispositivi nello stesso edificio e in edifici diversi. Tieni presenti problemi noti come le fluttuazioni e gli errori di alimentazione, poiché potrebbero essere utili per i problemi di infrastruttura.|

## <a name="see-also"></a>Vedere anche
 

[Pianificare la gestione di Microsoft teams Rooms con Azure monitor](azure-monitor-plan.md)

[Distribuire Gestione di Microsoft teams Rooms con Azure monitor](azure-monitor-deploy.md)
