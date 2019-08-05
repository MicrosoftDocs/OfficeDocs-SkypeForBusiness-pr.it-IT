---
title: Risolvere i problemi di gestione statistiche per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Riepilogo: leggere questo argomento per risolvere i problemi di distribuzione di gestione statistiche per Skype for Business Server.'
ms.openlocfilehash: b85ee6593413cce0aa5b7c76901dbbc6099107fd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195087"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>Risolvere i problemi di gestione statistiche per Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per risolvere i problemi di distribuzione di gestione statistiche per Skype for Business Server.
  
In questo argomento viene descritto come risolvere i problemi relativi alla distribuzione di gestione statistiche descrivendo gli eventi che potrebbero essere visualizzati nel log eventi dell'applicazione e le azioni appropriate che potrebbero essere necessarie per correggere l'evento. Questo argomento contiene le sezioni seguenti:
  
- [Eventi agente](troubleshoot.md#BKMK_Agent)
    
- [Eventi listener](troubleshoot.md#BKMK_Listener)
    
- [Problemi relativi al sito Web](troubleshoot.md#BKMK_Website)
    
## <a name="agent-events"></a>Eventi agente
<a name="BKMK_Agent"> </a>

- **1000** -non è possibile configurare il limitatore del processore (oggetto processo)-motivo sconosciuto
    
- **1001** -la limitazione del processo non è consentita nel processo (probabilmente già all'interno di un oggetto processo)
    
    L'agente viene eseguito all'interno di un oggetto processo di Windows per limitare automaticamente l'impronta di memoria. Se l'agente non si avvia e queste voci di evento sono presenti nel log eventi, non è possibile creare un'istanza dell'oggetto processo nel server. Per ovviare a questo problema, è possibile rimuovere il limite di memoria superiore modificando un valore nel file di configurazione:
    
  ```
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    Cercare "MaxProcessMemoryMB" e cambiare il valore in "0" come illustrato:
    
  ```
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > Se viene apportata questa modifica, l'agente utilizzerà \< in genere ancora 100 MB di memoria, ma non sarà limitato con forza a 300 MB come per l'impostazione predefinita. Se questa modifica viene eseguita, è consigliabile monitorare attentamente l'utilizzo della memoria per verificare che l'agente non consumi una grande quantità di memoria nel computer host. 
  
- **2000** -errore di inizializzazione del client
    
- **2001**-nessuna connessione può essere eseguita per il servizio in qualsiasi IP di origine
    
    Se l'agente non riesce a connettersi al computer del listener, verificare quanto segue:
    
1. Verificare che il servizio listener sia in uso nel computer listener. In caso contrario, assicurati che Redis sia in uso nel server e quindi riavvia il servizio listener.
    
    Controllare il log eventi di gestione statistiche nel computer listener per verificare che non ci siano problemi con il servizio listener di gestione statistiche.
    
2. Usare uno strumento di connettività come Telnet per verificare la connettività dal computer dell'agente al listener nella porta corretta.
    
    In caso contrario, verificare che la regola del firewall in arrivo sia abilitata nel computer del listener per il tipo di rete a cui è connesso il computer listener (privato/pubblico/dominio). Se il computer listener non è collegato a un dominio, la rete potrebbe essere elencata come pubblica e in questo caso le regole del firewall installate con gestione statistiche non verranno applicate per impostazione predefinita.
    
- **4000** — mancato download delle informazioni sul server da listener (motivo sconosciuto)
    
  - **4001** -server non trovato nella topologia del listener
    
    Questo errore si verifica se il server si connette correttamente al listener, ma il server non è stato aggiunto alla topologia nella cache del listener. Opzioni di risoluzione:
    
  - Verificare di aver seguito le istruzioni per l'importazione della topologia. Vedere [importare la topologia](deploy.md#BKMK_ImportTopology). 
    
  - Se l'agente si trova in un server non elencato nella topologia, ad esempio i nodi di un cluster SQL AlwaysOn, sarà necessario aggiungere manualmente l'agente seguendo le istruzioni in [importare la topologia](deploy.md#BKMK_ImportTopology).
    
  - **4002** — password di listener non valida
    
    La password crittografata che l'agente sta tentando di usare non corrisponde alla password del servizio nel listener stesso. Disinstallare l'agente e installarlo di nuovo usando la password del servizio corretta.
    
  - **4003** — mancata corrispondenza dell'identificazione personale del certificato
    
    L'identificazione personale del certificato assegnata all'agente in fase di installazione non corrisponde all'identificazione personale del certificato che il listener sta attualmente usando e quindi la connessione verrà rifiutata. Disinstallare l'agente e reinstallarlo usando l'identificazione personale del certificato corretto.
    
  - **4004** — risposta non valida o HttpStatusCode
    
    Il listener non risponde con uno stato previsto. 
    
  - Se la connessione viene inoltrata tramite proxy, verificare la configurazione del proxy.
    
  - Controllare il log degli stats del computer del listener per problemi relativi alla configurazione.
    
  - **4005** -non è possibile deserializzare il codice XML
    
    Le informazioni sul server nel server dei listener sono danneggiate o potrebbe essersi verificato un mancato confronto della versione tra l'agente e i computer del listener. Verificare che le versioni corrispondano e controllare il log eventi del listener per eventuali problemi.
    
## <a name="listener-events"></a>Eventi listener
<a name="BKMK_Listener"> </a>

- **10000** -motivo di errore di avvio sconosciuto (non recuperabile e il servizio si arresta/arresta in modo anomalo)
    
  - **10001** -problema di configurazione
    
    In genere, questo problema si verifica quando il file \PerfAgentListener.exe.config [listener_install_location] è stato modificato manualmente e non può essere letto dall'applicazione.
    
  - **10002** — errore di inizializzazione del listener http
    
    Questo evento viene in genere registrato quando l'ACL dell'URL non è stato impostato correttamente durante l'installazione o il certificato SSL non è valido. Verificare che il certificato della configurazione sia valido. In caso affermativo, reinstallare il listener seguendo le istruzioni in [deploy Statistics Manager](deploy.md#BKMK_Deploy).
    
  - **10003** — Redis failure
    
  - **10004** — errore di infrastruttura nella cache
    
  - **10007** — impostazioni (archiviate in Redis)
    
    Il listener non ha potuto contattare Redis o recuperare dati ben formati dalla cache e non può iniziare. Verificare che il servizio Redis sia avviato e configurato correttamente nel server.
    
  - **10005** -recupero/analisi delle informazioni sul server
    
    Le informazioni sulla topologia nella cache Redis non sono valide. Prima di tutto, provare a riavviare Redis e il listener. Se l'errore persiste, vedere [importare la topologia](deploy.md#BKMK_ImportTopology) per ricreare i dati della topologia.
    
- **10100** — riredi l'interruzione del ping
    
  - **10101** — Redis ping continua l'interruzione (ogni 60 secondi)
    
  - **30100** -riattiva l'interruzione di ping ripristinata
    
    Questi verranno registrati quando il listener non riesce a connettersi a Redis. Assicurarsi che ReDim sia avviato e che sia disponibile la connettività di rete tra listener e Redi.
    
- **10200** -l'interruzione della scrittura di redis
    
  - **10201** -l'interruzione della scrittura di redis continua (ogni 60 secondi)
    
  - **30100** -reredis per l'interruzione della scrittura risolto
    
    Questi verranno registrati quando il listener non può scrivere nella cache Redis. Assicurarsi che ReDim sia avviato e che sia disponibile la connettività di rete tra listener e Redi.
    
- **30000** -avvio corretto
    
    Registrato ogni volta che il listener viene avviato.
    
- **22000** -inizializzazione dell'agente di gestione statistiche riuscito.
    
- **23000** -inizializzazione di EventLogQueryManager succeeded (prima o dopo il fallimento)
    
- **24000** -inizializzazione di ServerInfo succeeded (prima o dopo il fallimento)
    
- **25000** -listener è di nuovo online dopo il mancato inserimento (o primo post riuscito)
    
- **5000** -inizio del listener offline per la registrazione dei dati
    
- **5001** -listener è ancora offline per un periodo di tempo prolungato
    
    Questi eventi possono essere utili per il monitoraggio/segnalazione/cancellazione dei problemi.
    
## <a name="website-issues"></a>Problemi relativi al sito Web
<a name="BKMK_Website"> </a>

- Istruzioni di accesso ripetitive in Chrome: si trattava di un bug risolto nella versione 1,1. Verificare di avere eseguito l'aggiornamento alla versione più recente di Statistics Manager se si vedono richieste di accesso ripetute nel browser Chrome. Per verificare la versione del sito Web in esecuzione:
    
  - In Esplora file aprire (directory predefinita)
    
  - Fai clic con il pulsante destro del mouse su StatsManHubWebSite. dll e visualizza le relative proprietà.
    
  - Se non è possibile trovare un computer nella visualizzazione orizzontale KHI o nella visualizzazione dettagli contatore, verificare che sia membro di un sito e di un pool. In caso contrario, non verrà visualizzata in tali visualizzazioni. Per informazioni sulla definizione di un sito e di un pool per un server nella topologia, vedere [importare la topologia](deploy.md#BKMK_ImportTopology).
    
  - La versione del prodotto verrà visualizzata nei dettagli della descrizione.
    
## <a name="for-more-information"></a>Per altre informazioni
<a name="BKMK_Website"> </a>

Per altre informazioni, vedere quanto segue:
  
- [Pianificare la gestione delle statistiche per Skype for Business Server](plan.md)
    
- [Distribuire Gestione statistiche per Skype for Business Server](deploy.md)
    
- [Aggiornare le statistiche di gestione per Skype for Business Server](upgrade.md)
