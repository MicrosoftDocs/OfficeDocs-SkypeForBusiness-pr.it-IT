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
description: 'Riepilogo: leggere questo argomento per risolvere i problemi relativi alla distribuzione di Statistics Manager per Skype for Business Server.'
ms.openlocfilehash: ea3d6f66003841e893ebe2dcc5d3fe02d0da125b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821776"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>Risoluzione dei problemi del gestore delle statistiche per Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per risolvere i problemi relativi alla distribuzione di Statistics Manager per Skype for Business Server.
  
In questo argomento viene descritto come risolvere i problemi relativi alla distribuzione di Gestione statistiche descrivendo gli eventi che potrebbero essere visualizzati nel registro eventi dell'applicazione e le azioni appropriate che è possibile intraprendere per rettificare l'evento. In questa sezione sono contenute le seguenti sezioni:
  
- [Eventi agente](troubleshoot.md#BKMK_Agent)
    
- [Eventi listener](troubleshoot.md#BKMK_Listener)
    
- [Problemi relativi ai siti Web](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a>Eventi agente
<a name="BKMK_Agent"> </a>

- **1000** - Impossibile impostare il limitatore del processore (oggetto processo) - Motivo sconosciuto
    
- **1001-** La limitazione dei processi non è consentita nel processo (probabilmente già all'interno di un oggetto processo)
    
    L'agente viene eseguito all'interno di un oggetto processo Windows per limitare automaticamente il footprint di memoria. Se l'agente non viene avviato e queste voci di evento sono presenti nel registro eventi, non è possibile creare un'istanza dell'oggetto processo nel server. Per risolvere questo problema, è possibile rimuovere il limite di memoria superiore modificando un valore nel file di configurazione:
    
  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    Cercare "MaxProcessMemoryMB" e modificare il valore in "0" come illustrato:
    
  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > Se viene apportata questa modifica, l'agente in genere continuerà a utilizzare 100 MB di memoria, ma non sarà forzatamente limitato a \< 300 MB come predefinito. Se viene apportata questa modifica, è consigliabile monitorare attentamente l'utilizzo della memoria per assicurarsi che l'agente non utilizzi una grande quantità di memoria nel computer host. 
  
- **2000** - Errore di inizializzazione del client
    
- **2001**- Non è stato possibile stabilire alcuna connessione al servizio in qualsiasi IP di origine
    
    Se l'agente non riesce a connettersi al computer listener, controllare quanto segue:
    
    1. Verificare che il servizio listener sia in esecuzione nel computer listener. In caso contrario, verificare che Redis sia in esecuzione su tale server e quindi riavviare il servizio listener.
        
        Controllare il registro eventi di Gestione statistiche nel computer listener per verificare che non vi siano problemi con il servizio Listener di Gestione statistiche stesso.
        
    2. Utilizzare uno strumento di connettività, ad esempio telnet, per verificare la connettività dal computer agente al listener sulla porta corretta.
        
        In caso contrario, verificare che la regola del firewall in ingresso sia abilitata nel computer listener per il tipo di rete a cui è connesso il computer listener (privato/pubblico/dominio). Se il computer listener non fa parte di un dominio, la rete potrebbe essere elencata come pubblica e in tal caso le regole del firewall installate con Gestione statistiche non verranno applicate per impostazione predefinita.
    
- **4000** - Errore durante il download delle informazioni sul server dal listener (motivo sconosciuto)
    
  - **4001** - Server non trovato nella topologia listener
    
    Questo errore si verifica se il server si connette correttamente al listener, ma il server non è stato aggiunto alla topologia nella cache del listener. Opzioni di risoluzione:
    
  - Assicurarsi di aver seguito le istruzioni per l'importazione della topologia. Vedere [Importare la topologia.](deploy.md#BKMK_ImportTopology) 
    
  - Se l'agente si trova in un server non elencato nella topologia (ad esempio, i nodi in un cluster AlwaysOn di SQL), sarà necessario aggiungere l'agente manualmente seguendo le istruzioni in [Importare](deploy.md#BKMK_ImportTopology)la topologia.
    
  - **4002** - Password listener non valida
    
    La password crittografata che l'agente sta tentando di utilizzare non corrisponde alla password del servizio nel listener stesso. Disinstallare l'agente e reinstallarlo utilizzando la password del servizio corretta.
    
  - **4003** - Certificate Thumbprint Mismatch
    
    L'identificazione personale del certificato data all'agente al momento dell'installazione non corrisponde all'identificazione personale nel certificato attualmente utilizzato dal listener e pertanto la connessione verrà rifiutata. Disinstallare l'agente e reinstallarlo utilizzando l'identificazione personale del certificato corretta.
    
  - **4004** - Risposta non valida o HttpStatusCode
    
    Il listener non risponde con uno stato previsto. 
    
  - Se la connessione è proxy, controlla la configurazione del proxy.
    
  - Controllare il registro StatsMan del computer listener per verificare la presenza di problemi di configurazione.
    
  - **4005** - Impossibile de-serializzare il codice XML
    
    Le informazioni sul server nel server listener sono danneggiate o potrebbe esserci una mancata corrispondenza di versione tra l'agente e i computer listener. Verificare che le versioni corrispondano e controllare la presenza di problemi nel registro eventi del listener.
    
## <a name="listener-events"></a>Eventi listener
<a name="BKMK_Listener"> </a>

- **10000** - Errore di avvio Motivo sconosciuto (irreversibile e il servizio si arresta/arresta in modo anomalo di conseguenza)
    
  - **10001** - Problema di configurazione
    
    In genere ciò si verifica quando il file [listener_install_location]\PerfAgentListener.exe.config è stato modificato manualmente e non può essere letto dall'applicazione.
    
  - **10002** - Errore di inizializzazione del listener HTTP
    
    Questo evento viene in genere registrato quando l'elenco di controllo di accesso url non è stato impostato correttamente durante l'installazione o il certificato SSL non è valido. Verificare che il certificato nella configurazione sia valido. In caso contrario, reinstallare il listener in base alle istruzioni in [Deploy Statistics Manager.](deploy.md#BKMK_Deploy)
    
  - **10003** - Errore Redis
    
  - **10004** - Errore dell'infrastruttura di memorizzazione nella cache
    
  - **10007** - Impostazioni (archiviate in redis)
    
    Il listener non è stato in grado di contattare Redis o recuperare dati ben formati dalla cache e non è stato possibile avviarsi. Verificare che il servizio Redis sia avviato e configurato correttamente nel server.
    
  - **10005** - Recupero/analisi delle informazioni sul server
    
    Le informazioni sulla topologia nella cache Redis non sono valide. Prima di tutto, tenta di riavviare Redis e il listener. Se l'errore persiste, vedere [Importare la topologia per](deploy.md#BKMK_ImportTopology) ricreare i dati della topologia.
    
- **10100** - Interruzione del PING di Redis
    
  - **10101** - Interruzione continuata di Redis PING (ogni 60 secondi)
    
  - **30100** - Redis PING outage restored
    
    Questi verranno registrati quando il listener non è in grado di connettersi a Redis. Assicurati che Redis sia avviato e che la connettività di rete tra Listener e Redis sia disponibile.
    
- **10200** - Interruzione della scrittura di Redis
    
  - **10201** - Interruzione di Redis Write continua (ogni 60 secondi)
    
  - **30100** - Risoluzione dell'interruzione della scrittura di Redis
    
    Questi verranno registrati quando il listener non è in grado di scrivere nella cache Redis. Assicurati che Redis sia avviato e che la connettività di rete tra Listener e Redis sia disponibile.
    
- **30000** - Avviato correttamente
    
    Registrato ogni volta che il listener viene avviato.
    
- **22000-** Inizializzazione dell'agente di gestione delle statistiche completata.
    
- **23000** - Inizializzazione di EventLogQueryManager completata (prima volta o dopo un errore)
    
- **24000** - Inizializzazione di serverinfo completata (prima volta o dopo un errore)
    
- **25000** - Listener è di nuovo online dopo la mancata pubblicazione (o il primo post riuscito)
    
- **5000** - Inizio del listener offline per l'inserimento di dati
    
- **5001** - Listener ancora offline per un periodo prolungato
    
    Questi eventi possono essere utili per il monitoraggio,l'avviso/la cancellazione dei problemi.
    
## <a name="website-issues"></a>Problemi relativi ai siti Web
<a name="BKMK_Website"> </a>

- Richieste di accesso ripetitive in Chrome: si tratta di un bug risolto nella versione 1.1. Assicurarsi di aver eseguito l'aggiornamento all'ultima versione di Gestione statistiche se vengono visualizzate richieste di accesso ripetute nel browser Chrome. Per verificare la versione del sito Web in esecuzione:
    
  - In Esplora file apri (directory predefinita)
    
  - Fai clic con il StatsManHubWebSite.dll clic con il pulsante destro del mouse e visualizzane le proprietà.
    
  - Se non è possibile trovare un computer nella visualizzazione KHI Orizzontale o Dettagli contatore, verificare che sia membro di un sito e di un pool. In caso contrario, non verrà visualizzato in tali visualizzazioni. Per informazioni sulla definizione di un sito e di un pool per un server nella topologia, vedere [Import the topology.](deploy.md#BKMK_ImportTopology)
    
  - La versione del prodotto verrà visualizzata nei dettagli della descrizione.
    
## <a name="for-more-information"></a>Ulteriori informazioni
<a name="BKMK_Website"> </a>

Per ulteriori informazioni, vedere gli argomenti seguenti:
  
- [Pianificare il gestore delle statistiche per Skype for Business Server](plan.md)
    
- [Distribuire il gestore delle statistiche per Skype for Business Server](deploy.md)
    
- [Aggiornare il gestore delle statistiche per Skype for Business Server](upgrade.md)
