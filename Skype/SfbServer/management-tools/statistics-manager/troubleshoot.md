---
title: Risoluzione dei problemi del gestore delle statistiche per Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Riepilogo: leggere questo argomento per risolvere i problemi relativi alla distribuzione di Gestione statistiche per Skype for Business Server.'
ms.openlocfilehash: 6e6edefe8d6070a917f817b3b6d79bf35ff36599
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857343"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>Risoluzione dei problemi del gestore delle statistiche per Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per risolvere i problemi relativi alla distribuzione di Gestione statistiche per Skype for Business Server.
  
In questo argomento viene descritto come risolvere i problemi relativi alla distribuzione di Gestione statistiche descrivendo gli eventi che potrebbero essere visualizzati nel registro eventi dell'applicazione e le azioni appropriate da eseguire per correggere l'evento. In questa sezione sono contenute le seguenti sezioni:
  
- [Eventi agente](troubleshoot.md#BKMK_Agent)
    
- [Eventi listener](troubleshoot.md#BKMK_Listener)
    
- [Problemi relativi al sito Web](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a>Eventi agente
<a name="BKMK_Agent"> </a>

- **1000** - Impossibile impostare il limitatore del processore (oggetto Processo) - Motivo sconosciuto
    
- **1001** - La limitazione dei processi non è consentita nel processo (probabilmente già all'interno di un oggetto processo)
    
    L'agente viene eseguito all'interno di un Windows processo per limitare automaticamente il footprint di memoria. Se l'agente non viene avviato e queste voci di evento sono presenti nel registro eventi, non è possibile creare un'istanza dell'oggetto processo nel server. Per risolvere questo problema, è possibile rimuovere il limite di memoria superiore modificando un valore nel file di configurazione:
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    Cercare "MaxProcessMemoryMB" e modificare il valore in "0" come illustrato:
    
  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > Se questa modifica viene apportata, l'agente in genere continuerà a utilizzare 100 MB di memoria, ma non sarà forzatamente limitata a 300 MB come è \< l'impostazione predefinita. Se questa modifica viene apportata, è consigliabile monitorare attentamente l'utilizzo della memoria per assicurarsi che l'agente non utilizzi una grande quantità di memoria nel computer host. 
  
- **2000** - Errore di inizializzazione del client
    
- **2001-** Non è stato possibile stabilire alcuna connessione al servizio in un IP di origine
    
    Se l'agente non è in grado di connettersi al computer listener, verificare quanto segue:
    
    1. Verificare che il servizio Listener sia in esecuzione nel computer listener. In caso contrario, verificare che Redis sia in esecuzione sul server e quindi riavviare il servizio Listener.
        
        Controllare il registro eventi di Gestione statistiche nel computer listener per verificare che non vi siano problemi con il servizio Listener di Gestione statistiche stesso.
        
    2. Utilizzare uno strumento di connettività, ad esempio telnet, per verificare la connettività dal computer agente al listener sulla porta corretta.
        
        In caso contrario, verificare che la regola del firewall in ingresso sia abilitata nel computer listener per il tipo di rete a cui è connesso il computer listener (privato/pubblico/dominio). Se il computer listener non fa parte di un dominio, la rete potrebbe essere elencata come pubblica e in tal caso le regole del firewall installate con Gestione statistiche non verranno applicate per impostazione predefinita.
    
- **4000** - Errore durante il download delle informazioni sul server dal listener (motivo sconosciuto)
    
  - **4001** - Server non trovato nella topologia listener
    
    Questo errore si verifica se il server si connette correttamente al listener, ma il server non è stato aggiunto alla topologia nella cache del listener. Opzioni di risoluzione:
    
  - Assicurarsi di aver seguito le istruzioni per l'importazione della topologia. Vedere [Import the topology](deploy.md#BKMK_ImportTopology). 
    
  - Se l'agente si trova in un server non elencato nella topologia( ad esempio, i nodi in un cluster AlwaysOn di SQL), sarà necessario aggiungere manualmente l'agente seguendo le istruzioni in [Importare](deploy.md#BKMK_ImportTopology)la topologia .
    
  - **4002** - Password listener non valida
    
    La password crittografata che l'agente sta tentando di utilizzare non corrisponde alla password del servizio nel listener stesso. Disinstallare l'agente e reinstallarlo utilizzando la password del servizio corretta.
    
  - **4003** - Identificazione personale certificato non corrispondente
    
    L'identificazione personale del certificato assegnato all'agente al momento dell'installazione non corrisponde all'identificazione personale nel certificato attualmente utilizzato dal listener e pertanto la connessione verrà rifiutata. Disinstallare l'agente e reinstallarlo utilizzando l'identificazione personale del certificato corretta.
    
  - **4004** - Risposta non valida o HttpStatusCode
    
    Il listener non risponde con uno stato previsto. 
    
  - Se la connessione è proxy, controllare la configurazione del proxy.
    
  - Controllare il registro StatsMan del computer listener per eventuali problemi di configurazione.
    
  - **4005** - Impossibile de-serializzare il codice XML
    
    Le informazioni sul server nel server Listener sono danneggiate o potrebbe esserci una mancata corrispondenza di versione tra l'agente e i computer listener. Verificare che le versioni corrispondano e controllare la presenza di problemi nel registro eventi listener.
    
## <a name="listener-events"></a>Eventi listener
<a name="BKMK_Listener"> </a>

- **10000** - Errore di avvio Motivo sconosciuto (irreversibile e il servizio si arresterà/arresterà in modo anomalo di conseguenza)
    
  - **10001** - Problema di configurazione
    
    In genere ciò si verifica quando il file [listener_install_location]\PerfAgentListener.exe.config è stato modificato manualmente e non può essere letto dall'applicazione.
    
  - **10002** - Errore di inizializzazione del listener HTTP
    
    Questo evento viene in genere registrato quando l'elenco di controllo di accesso url non è stato impostato correttamente durante l'installazione o il certificato SSL non è valido. Verificare che il certificato nella configurazione sia valido. In caso contrario, reinstallare il listener in base alle istruzioni riportate in [Deploy Statistics Manager.](deploy.md#BKMK_Deploy)
    
  - **10003** - Errore redis
    
  - **10004** - Errore Caching'infrastruttura
    
  - **10007** — Impostazioni (archiviato in redis)
    
    Il listener non è stato in grado di contattare Redis o recuperare dati ben formati dalla cache e non è stato possibile avviarsi. Verificare che il servizio Redis sia avviato e configurato correttamente nel server.
    
  - **10005** - Recupero/analisi delle informazioni sul server
    
    Le informazioni sulla topologia nella cache di Redis non sono valide. Prima di tutto, tenta di riavviare Redis e listener. Se l'errore persiste, vedere [Import the topology](deploy.md#BKMK_ImportTopology) to recreate the topology data.
    
- **10100** - Interruzione ping redis
    
  - **10101** - Interruzione continuata di Redis PING (ogni 60 secondi)
    
  - **30100** - Ripristino dell'interruzione del PING di Redis
    
    Questi verranno registrati quando il listener non è in grado di connettersi a Redis. Verificare che Redis sia avviato e che sia disponibile la connettività di rete tra Listener e Redis.
    
- **10200** - Redis Write outage
    
  - **10201** - Continua l'interruzione di Redis Write (ogni 60 secondi)
    
  - **30100** - Risoluzione dell'interruzione di Redis Write
    
    Questi verranno registrati quando il listener non è in grado di scrivere nella cache di Redis. Verificare che Redis sia avviato e che sia disponibile la connettività di rete tra Listener e Redis.
    
- **30000** - Avviato correttamente
    
    Registrato ogni volta che il listener viene avviato.
    
- **22000-** Inizializzazione dell'agente di gestione delle statistiche completata.
    
- **23000** - Inizializzazione di EventLogQueryManager riuscita (prima volta o dopo un errore)
    
- **24000** - Inizializzazione di serverinfo completata (prima volta o dopo un errore)
    
- **25000** - Listener tornato online dopo la mancata pubblicazione (o il primo post riuscito)
    
- **5000** - Inizio del listener offline per la pubblicazione dei dati
    
- **5001** - Listener ancora offline per un periodo prolungato
    
    Questi eventi possono essere utili per i problemi di monitoraggio/avviso/cancellazione.
    
## <a name="website-issues"></a>Problemi relativi al sito Web
<a name="BKMK_Website"> </a>

- Richieste di accesso ripetitive in Chrome: si tratta di un bug risolto nella versione 1.1. Assicurati di aver eseguito l'aggiornamento alla versione più recente di Gestione statistiche se nel browser Chrome vengono visualizzate richieste di accesso ripetute. Per verificare la versione del sito Web in esecuzione:
    
  - In Esplora file apri (directory predefinita)
    
  - Fai clic con il pulsante destro del StatsManHubWebSite.dll e visualizzane le proprietà.
    
  - Se non è possibile trovare un computer nella visualizzazione KHI Orizzontale o Dettagli contatore, verificare che sia membro di un sito e di un pool. In caso contrario, non verrà visualizzato in tali visualizzazioni. Per informazioni sulla definizione di un sito e di un pool per un server nella topologia, vedere [Import the topology](deploy.md#BKMK_ImportTopology).
    
  - La versione del prodotto verrà visualizzata nei dettagli della descrizione.
    
## <a name="for-more-information"></a>Ulteriori informazioni
<a name="BKMK_Website"> </a>

Per ulteriori informazioni, vedere gli argomenti seguenti:
  
- [Pianificare il gestore delle statistiche per Skype for Business Server](plan.md)
    
- [Distribuire il gestore delle statistiche per Skype for Business Server](deploy.md)
    
- [Aggiornare il gestore delle statistiche per Skype for Business Server](upgrade.md)
