---
title: Risoluzione dei problemi del gestore delle statistiche per Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 946189fa-521f-455c-9762-904e7e41b791
description: 'Riepilogo: leggere questo argomento per risolvere i problemi di distribuzione di Statistics Manager per Skype for Business Server.'
ms.openlocfilehash: a7604b15826ee55e127cd24447b0557b24b78548
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675278"
---
# <a name="troubleshoot-statistics-manager-for-skype-for-business-server"></a>Risoluzione dei problemi del gestore delle statistiche per Skype for Business Server

**Riepilogo:** Leggere questo argomento per risolvere i problemi di distribuzione di Statistics Manager per Skype for Business Server.

Questo argomento descrive come risolvere i problemi relativi alla distribuzione di Statistics Manager descrivendo gli eventi che potrebbero essere visualizzati nel registro eventi dell'applicazione e le azioni appropriate che è possibile eseguire per rettificare l'evento. In questa sezione sono contenute le seguenti sezioni:

- [Eventi dell'agente](troubleshoot.md#BKMK_Agent)

- [Eventi listener](troubleshoot.md#BKMK_Listener)

- [Problemi del sito Web](troubleshoot.md#BKMK_Website)

## <a name="agent-events"></a>Eventi dell'agente
<a name="BKMK_Agent"> </a>

- **1000** - Impossibile configurare il limitatore del processore (oggetto processo) - Motivo sconosciuto

- **1001** - La limitazione del processo non è consentita nel processo (probabilmente già all'interno di un oggetto processo)

    L'agente viene eseguito all'interno di un oggetto processo Windows per limitarne automaticamente il footprint di memoria. Se l'agente non viene avviato e queste voci di evento sono presenti nel registro eventi, non è possibile creare un'istanza dell'oggetto processo nel server. Per ovviare a questo errore, è possibile rimuovere il limite di memoria superiore modificando un valore nel file di configurazione:

  ```console
  C:\Program Files\Skype for Business Server StatsMan Agent\PerfAgent.exe.config
  ```

    Cercare "MaxProcessMemoryMB" e modificare il valore in "0" come illustrato di seguito:

  ```xml
  <setting name="MaxProcessMemoryMB" serializeAs="String"> <value>300</value> </setting>
  ```

    > [!NOTE]
    > Se questa modifica viene apportata, l'agente in genere utilizzerà \< comunque 100 MB di memoria, ma non sarà limitato forzatamente a 300 MB come predefinito. Se questa modifica viene apportata, è consigliabile monitorare attentamente l'utilizzo della memoria per garantire che l'agente non usi una grande quantità di memoria nel computer host.

- **2000** - Errore di inizializzazione del client

- **2001**: non è stato possibile effettuare alcuna connessione al servizio su qualsiasi indirizzo IP di origine

  Se l'agente non riesce a connettersi al computer listener, controllare quanto segue:

  1. Verificare che il servizio Listener sia in esecuzione nel computer listener. In caso contrario, verificare che Redis sia in esecuzione in tale server e quindi riavviare il servizio Listener.

     Controllare il registro eventi di Gestione statistiche nel computer listener per assicurarsi che non si verifichino problemi con il servizio listener di Gestione statistiche.

  2. Usare uno strumento di connettività, ad esempio telnet, per verificare la connettività dal computer agente al listener sulla porta corretta.

     In caso contrario, verificare che la regola del firewall in ingresso sia abilitata nel computer listener per il tipo di rete a cui è connesso il computer listener (privato/pubblico/dominio). Se il computer listener non è aggiunto a un dominio, la rete potrebbe essere elencata come pubblica e in questo caso le regole del firewall installate con Gestione statistiche non verranno applicate per impostazione predefinita.

- **4000** - Errore di download delle informazioni del server dal listener (motivo sconosciuto)

  - **4001** - Server non trovato nella topologia del listener

    Questo errore si verifica se il server si connette correttamente al listener, ma il server non è stato aggiunto alla topologia nella cache del listener. Opzioni di risoluzione:

  - Assicurarsi di aver seguito le istruzioni per l'importazione della topologia. Vedere [Importare la topologia](deploy.md#BKMK_ImportTopology).

  - Se l'agente si trova in un server non elencato nella topologia, ad esempio i nodi di un cluster SQL AlwaysOn, sarà necessario aggiungere manualmente l'agente seguendo le istruzioni riportate in [Importa la topologia](deploy.md#BKMK_ImportTopology).

  - **4002** - Password listener non valida

    La password crittografata che l'agente sta tentando di usare non corrisponde alla password del servizio nel listener stesso. Disinstallare l'agente e reinstallarlo usando la password del servizio corretta.

  - **4003** — Mancata corrispondenza dell'identificazione personale del certificato

    L'identificazione personale del certificato fornita all'agente in fase di installazione non corrisponde all'identificazione personale nel certificato attualmente in uso dal listener e pertanto la connessione verrà rifiutata. Disinstallare l'agente e reinstallarlo usando l'identificazione personale del certificato corretta.

  - **4004** - Risposta non valida o HttpStatusCode

    Il listener non risponde con uno stato previsto.

  - Se la connessione è proxy, controllare la configurazione del proxy.

  - Controllare il log StatsMan del computer listener per verificare la presenza di problemi di configurazione.

  - **4005** - Impossibile deserializzare il codice XML

    Le informazioni del server nel server listener sono danneggiate o potrebbe verificarsi una mancata corrispondenza della versione tra l'agente e i computer listener. Verificare che le versioni corrispondano e controllare la presenza di problemi nel registro eventi del listener.

## <a name="listener-events"></a>Eventi listener
<a name="BKMK_Listener"> </a>

- **10000** - Errore di avvio Motivo sconosciuto (questi sono irrecuperabili e di conseguenza il servizio si arresta/arresta in modo anomalo)

  - **10001** — Problema di configurazione

    Ciò si verifica in genere quando il file [listener_install_location]\PerfAgentListener.exe.config è stato modificato manualmente e non può essere letto dall'applicazione.

  - **10002** - Errore di inizializzazione del listener HTTP

    Questo evento verrà in genere registrato quando l'ACL URL non è stato impostato correttamente durante l'installazione o il certificato SSL non è valido. Verificare che il certificato nella configurazione sia valido. In caso affermativo, reinstallare il listener in base alle istruzioni riportate in [Deploy Statistics Manager (Distribuire Gestione statistiche](deploy.md#BKMK_Deploy)).

  - **10003** — Errore di Redis

  - **10004** — errore dell'infrastruttura Caching

  - **10007** — Impostazioni (archiviato in redis)

    Il listener non è riuscito a contattare Redis o a recuperare dati ben formati dalla cache e non è stato possibile avviarne l'avvio. Verificare che il servizio Redis sia avviato e configurato correttamente nel server.

  - **10005** — Recupero/analisi delle informazioni del server

    Le informazioni sulla topologia nella cache Redis non sono valide. Provare prima di tutto a riavviare Redis e il listener. Se l'errore persiste, vedere [Importare la topologia](deploy.md#BKMK_ImportTopology) per ricreare i dati della topologia.

- **10100** — Interruzione di Ping Redis

  - **10101** — Redis PING ha continuato l'interruzione (ogni 60 secondi)

  - **30100** - Interruzione ping Redis ripristinata

    Questi verranno registrati quando il listener non riesce a connettersi a Redis. Assicurarsi che Redis sia avviato e che sia disponibile la connettività di rete tra il listener e Redis.

- **10200** - Interruzione della scrittura di Redis

  - **10201** - Interruzione della scrittura di Redis continua (ogni 60 secondi)

  - **30100** - Risoluzione dell'interruzione della scrittura di Redis

    Questi verranno registrati quando il listener non può scrivere nella cache Redis. Assicurarsi che Redis sia avviato e che sia disponibile la connettività di rete tra il listener e Redis.

- **30000** - Avviato correttamente

    Registrato ogni volta che viene avviato il listener.

- **22000** - Inizializzazione dell'agente di Statistics Manager completata.

- **23000** - Inizializzazione di EventLogQueryManager completata (prima volta o dopo l'esito negativo)

- **24000** - Inizializzazione di serverinfo completata (prima volta o dopo l'errore)

- **25000** - Il listener è di nuovo online dopo la mancata pubblicazione (o il primo post riuscito)

- **5000** — Avvio del listener offline per la pubblicazione dei dati

- **5001** — Il listener è ancora offline per un periodo prolungato

    Questi eventi possono essere utili per il monitoraggio, l'avviso e la cancellazione dei problemi.

## <a name="website-issues"></a>Problemi del sito Web
<a name="BKMK_Website"> </a>

- Richieste di accesso ripetitive in Chrome: si tratta di un bug risolto nella versione 1.1. Assicurarsi di aver eseguito l'aggiornamento alla versione più recente di Statistics Manager se vengono visualizzate ripetute richieste di accesso nel browser Chrome. Per verificare la versione del sito Web in esecuzione:

  - In Esplora file aprire (directory predefinita)

  - Fare clic con il pulsante destro del mouse su StatsManHubWebSite.dll e visualizzarne le proprietà.

  - Se non è possibile trovare un computer nella visualizzazione ORIZZONTALe KHI o nella visualizzazione Dettagli contatore, assicurarsi che sia un membro di un sito e un pool. In caso contrario, non verrà visualizzato in tali visualizzazioni. Per informazioni sulla definizione di un sito e di un pool per un server nella topologia, vedere [Importare la topologia](deploy.md#BKMK_ImportTopology).

  - La versione del prodotto verrà visualizzata nei dettagli della descrizione.

## <a name="for-more-information"></a>Ulteriori informazioni
<a name="BKMK_Website"> </a>

Per ulteriori informazioni, vedere gli argomenti seguenti:

- [Pianificare il gestore delle statistiche per Skype for Business Server](plan.md)

- [Distribuire il gestore delle statistiche per Skype for Business Server](deploy.md)

- [Aggiornare il gestore delle statistiche per Skype for Business Server](upgrade.md)
