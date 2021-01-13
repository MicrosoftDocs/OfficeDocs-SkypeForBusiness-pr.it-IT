---
title: Risoluzione dei problemi del gestore delle statistiche per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Riepilogo: leggere questo argomento per la risoluzione dei problemi relativi alla distribuzione di gestione delle statistiche per Skype for Business Server.'
ms.openlocfilehash: ea3d6f66003841e893ebe2dcc5d3fe02d0da125b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821776"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>Risoluzione dei problemi del gestore delle statistiche per Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per risolvere i problemi relativi alla distribuzione di statistica Manager per Skype for Business Server.
  
In questo argomento viene descritto come risolvere i problemi relativi alla distribuzione di gestione delle statistiche descrivendo gli eventi che potrebbero essere visualizzati nel registro eventi dell'applicazione e le azioni appropriate che è possibile eseguire per rettificare l'evento. In questa sezione sono contenute le seguenti sezioni:
  
- [Eventi agente](troubleshoot.md#BKMK_Agent)
    
- [Eventi listener](troubleshoot.md#BKMK_Listener)
    
- [Problemi relativi ai siti Web](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a>Eventi agente
<a name="BKMK_Agent"> </a>

- **1000** -Impossibile impostare il limiter del processore (oggetto Job)-motivo sconosciuto
    
- **1001** -la limitazione dei processi non è consentita per il processo (probabilmente già all'interno di un oggetto Job)
    
    L'agente viene eseguito all'interno di un oggetto processo di Windows per limitare automaticamente il relativo footprint di memoria. Se l'agente non si avvia e queste voci di evento sono presenti nel registro eventi, l'oggetto Job non è in grado di creare un'istanza sul server. Per ovviare a questo, è possibile rimuovere il limite massimo di memoria cambiando un valore nel file di configurazione:
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    Cercare "MaxProcessMemoryMB" e cambiare il valore su "0" come mostrato nell'esempio:
    
  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > Se viene apportata questa modifica, l'agente consumerà generalmente \< 100 MB di memoria, tuttavia non sarà limitato con forza a 300 MB come è il valore predefinito. Se viene apportata questa modifica, è consigliabile monitorare l'utilizzo della memoria per garantire che l'agente non consumi una quantità elevata di memoria nel computer host. 
  
- **2000** -errore di inizializzazione del client
    
- **2001**-nessuna connessione può essere effettuata per il servizio su qualsiasi IP di origine
    
    Se l'agente non è in grado di connettersi al computer listener, controllare quanto segue:
    
    1. Verificare che il servizio listener sia in esecuzione nel computer listener. In caso contrario, verificare che ReDim sia in esecuzione su tale server e quindi riavviare il servizio listener.
        
        Controllare il registro eventi di gestione statistica sul computer listener per assicurarsi che non vi siano problemi con il servizio listener di gestione delle statistiche.
        
    2. Utilizzare uno strumento di connettività come Telnet per verificare la connettività dal computer dell'agente al listener sulla porta corretta.
        
        In caso contrario, verificare che la regola del firewall in ingresso sia abilitata nel computer listener per il tipo di rete a cui è connesso il computer listener (privato/pubblico/dominio). Se il computer listener non è aggiunto a un dominio, la rete potrebbe essere elencata come pubblica e, in tal caso, le regole del firewall installate con gestione statistiche non verranno applicate per impostazione predefinita.
    
- **4000** — mancato download delle informazioni del server dal listener (motivo sconosciuto)
    
  - **4001** -server non trovato nella topologia del listener
    
    Questo errore si verifica se il server si connette correttamente al listener, ma il server non è stato aggiunto alla topologia nella cache del listener. Opzioni di risoluzione:
    
  - Assicurarsi di aver seguito le istruzioni per importare la topologia. Vedere [importare la topologia](deploy.md#BKMK_ImportTopology). 
    
  - Se l'agente si trova in un server non elencato nella topologia, ad esempio i nodi di un cluster di SQL AlwaysOn, è necessario aggiungere manualmente l'agente attenendosi alle istruzioni [riportate in importare la topologia](deploy.md#BKMK_ImportTopology).
    
  - **4002** — password del listener non valida
    
    La password crittografata che l'agente sta tentando di utilizzare non corrisponde alla password del servizio sul listener stesso. Disinstallare l'agente e installarlo di nuovo utilizzando la password del servizio corretta.
    
  - **4003** -mancata corrispondenza dell'identificazione personale del certificato
    
    L'identificazione personale del certificato fornita all'agente al momento dell'installazione non corrisponde all'identificazione personale del certificato utilizzato dal listener e, pertanto, la connessione verrà rifiutata. Disinstallare l'agente e installarlo di nuovo utilizzando l'identificazione personale del certificato corretto.
    
  - **4004** -risposta non valida o HttpStatusCode
    
    Il listener non risponde con uno stato previsto. 
    
  - Se la connessione viene inoltrata, controllare la configurazione del proxy.
    
  - Controllare il registro di statistica del computer del listener per risolvere i problemi relativi alla configurazione.
    
  - **4005** -Impossibile deserializzare il codice XML
    
    Le informazioni sul server del listener sono danneggiate oppure la mancata corrispondenza tra l'agente e i computer del listener può essere inesistente. Verificare che le versioni corrispondano e controllare il registro eventi del listener per individuare eventuali problemi.
    
## <a name="listener-events"></a>Eventi listener
<a name="BKMK_Listener"> </a>

- **10000** -errore di avvio per motivi sconosciuti (non recuperabili e il servizio si arresterà o si arresterà a causa di un arresto)
    
  - **10001** — problema di configurazione
    
    In genere, questo si verificherà quando il file [listener_install_location] \PerfAgentListener.exe.config è stato modificato manualmente e non può essere letto dall'applicazione.
    
  - **10002** -errore di inizializzazione del listener http
    
    Questo evento viene generalmente registrato quando l'ACL dell'URL non è stato impostato correttamente durante l'installazione o il certificato SSL non è valido. Verificare che il certificato nella configurazione sia valido. In tal caso, reinstallare il listener seguendo le istruzioni riportate in [deploy Statistics Manager](deploy.md#BKMK_Deploy).
    
  - **10003** -ReDim failure
    
  - **10004** — errore dell'infrastruttura di memorizzazione nella cache
    
  - **10007** -impostazioni (archiviate in ReDim)
    
    Il listener non è stato in grado di contattare ReDim o di recuperare i dati ben formati dalla cache e non è stato possibile avviarli. Verificare che il servizio ReDim sia stato avviato e configurato correttamente nel server.
    
  - **10005** -recupero/analisi delle informazioni sul server
    
    Le informazioni sulla topologia nella cache di ReDim non sono valide. Per prima cosa, provare a riavviare ReDim e il listener. Se l'errore persiste, vedere [importare la topologia](deploy.md#BKMK_ImportTopology) per ricreare i dati della topologia.
    
- **10100** — ReDim l'interruzione del ping
    
  - **10101** : ReDim continua l'interruzione del ping (ogni 60 secondi)
    
  - **30100** — riattiva l'interruzione del ping ripristinata
    
    Tali operazioni verranno registrate quando il listener non è in grado di connettersi a ReDim. Verificare che ReDim sia stato avviato e che sia disponibile la connettività di rete tra listener e ReDim.
    
- **10200** -ReDim Write blackout
    
  - **10201** -le interruzioni di scrittura di ReDim sono continuate (ogni 60 secondi)
    
  - **30100** -ReDim Write blackout risolto
    
    Tali operazioni verranno registrate quando il listener non è in grado di scrivere nella cache di ReDim. Verificare che ReDim sia stato avviato e che sia disponibile la connettività di rete tra listener e ReDim.
    
- **30000** -avviato con esito positivo
    
    Registrato ogni volta che il listener è stato avviato.
    
- **22000** -inizializzazione dell'agente di gestione delle statistiche con esito positivo.
    
- **23000** -inizializzazione di EventLogQueryManager completata (prima o dopo la mancata esecuzione)
    
- **24000** -inizializzazione di ServerInfo completata (prima o dopo la mancata esecuzione)
    
- **25000** -listener è tornato online dopo la mancata esecuzione del post (o del primo post con esito positivo)
    
- **5000** — inizio del listener offline per la registrazione dei dati
    
- **5001** -listener è ancora offline per un periodo di tempo prolungato
    
    Questi eventi possono essere utili per il monitoraggio/l'avviso o la cancellazione dei problemi.
    
## <a name="website-issues"></a>Problemi relativi ai siti Web
<a name="BKMK_Website"> </a>

- Prompt di accesso ripetitivi in Chrome-questo è un bug che è stato risolto nella versione 1,1. Assicurarsi di aver eseguito l'aggiornamento alla versione più recente di gestione statistiche se vengono visualizzate le richieste di accesso ripetute nel browser Chrome. Per verificare la versione del sito Web in esecuzione:
    
  - In Esplora file aprire (directory predefinita)
    
  - Fare clic con il pulsante destro del mouse su StatsManHubWebSite.dll e visualizzarne le proprietà.
    
  - Se non è possibile trovare un computer nella visualizzazione orizzontale di KHI o nella visualizzazione dettagli contatore, verificare che sia membro di un sito e di un pool. In caso contrario, non verrà visualizzato nelle visualizzazioni. Per informazioni sulla definizione di un sito e di un pool per un server nella topologia, vedere [importare la topologia](deploy.md#BKMK_ImportTopology).
    
  - La versione del prodotto verrà visualizzata nei dettagli della descrizione.
    
## <a name="for-more-information"></a>Ulteriori informazioni
<a name="BKMK_Website"> </a>

Per ulteriori informazioni, vedere gli argomenti seguenti:
  
- [Pianificare il gestore delle statistiche per Skype for Business Server](plan.md)
    
- [Distribuire il gestore delle statistiche per Skype for Business Server](deploy.md)
    
- [Aggiornare il gestore delle statistiche per Skype for Business Server](upgrade.md)
