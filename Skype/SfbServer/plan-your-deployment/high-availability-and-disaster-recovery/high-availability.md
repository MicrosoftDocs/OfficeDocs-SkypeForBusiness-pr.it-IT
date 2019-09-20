---
title: Disponibilità elevata e gestione del pool Front-End
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: Informazioni sulla gestione del pool Front-end in Skype for Business Server, inclusi i pool di gestione, la perdita del quorum e i passaggi speciali per i pool con solo due server front-end.
ms.openlocfilehash: e42e192d224d509356203c059751624fc706707b
ms.sourcegitcommit: a6e44256c024fc3953cfd6a511ee024c4c7b8408
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "37047093"
---
# <a name="front-end-pool-high-availability-and-management"></a>Disponibilità elevata e gestione del pool Front-End
 
Informazioni sulla gestione del pool Front-end in Skype for Business Server, inclusi i pool di gestione, la perdita del quorum e i passaggi speciali per i pool con solo due server front-end.
  
In Skype for Business Server l'architettura dei pool Front-End usa un modello di sistemi distribuiti, con i dati di ogni utente conservati in tutti e tre i server front-end nel pool. È consigliabile che tutti i pool di front end di Enterprise Edition includano almeno tre server front-end. 
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Pianificazione per la gestione dei pool Front-End

 Skype for Business Server usa un modello di sistemi distribuiti basato su un tessuto Windows. In questo modello i dati importanti per ogni utente e conferenza sono archiviati in tre server front-end in un pool Front-end. Questi tre server che archiviano un determinato set di dati sono calledreplicas.
  
Con il modello distribuito per i pool Front-End, è necessario che un determinato numero di server del pool sia in funzione per il pool. Esistono due modalità di perdita per un pool.
  
- Perdita del quorum a livello di gruppo di routing causata da server di replica non sufficienti per un determinato gruppo di routing. Un gruppo di routing è un insieme di utenti ospitati nel pool. Ogni gruppo di routing include tre repliche nel pool: una replica primaria e due repliche secondarie.
    
- Perdita del quorum a livello di pool, causata quando i server di seeding non sono sufficienti in uso nel pool. 
    
### <a name="routing-group-level-quorum-loss"></a>Perdita del quorum a livello di gruppo di routing

La prima volta che si avvia un nuovo pool Front-End, è essenziale che il 85% dei server sia installato e in esecuzione, come illustrato nella tabella seguente. Se sono in uso meno server, i servizi potrebbero essere bloccati nello stato iniziale e il pool potrebbe non iniziare.
  
|Numero totale di server nel pool  <br/> |Numero di server che devono essere in esecuzione per il pool da avviare per la prima volta  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3  <br/> |3  <br/> |
|4  <br/> |3  <br/> |
|5  <br/> |4  <br/> |
|6  <br/> |5  <br/> |
|7  <br/> |5  <br/> |
|8  <br/> |6  <br/> |
|9  <br/> |7  <br/> |
|10  <br/> |8  <br/> |
|11  <br/> |9  <br/> |
|12  <br/> |10  <br/> |
   
Ogni volta che il pool viene avviato, è necessario avviare 85% dei server (come illustrato nella tabella precedente). Se non è possibile avviare questo numero di server (ma è possibile avviare abbastanza server in modo che non si sia in perdita di quorum a livello di pool), `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` è possibile usare il cmdlet per consentire al pool di recuperare da questa perdita di quorum a livello di gruppo di routing ed eseguire lo stato di avanzamento. Per altre informazioni su come usare questo cmdlet, vedere [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps). 
  
> [!NOTE]
> In pool con un numero pari di server, Skype for Business Server usa il database SQL primario come testimone. In un pool come questo, se si arresta il database principale e si passa alla copia speculare e si arresta un numero sufficiente di server front-end in modo che non sia sufficiente eseguire in base alla tabella precedente, l'intero pool verrà disattivato. Per altre informazioni, Vedi [Witness mirroring del database](https://go.microsoft.com/fwlink/?LinkId=393672). 
  
#### <a name="pool-level-quorum-loss"></a>Perdita del quorum a livello di pool

Affinché un pool Front-end funzioni affatto, non può essere in perdita di quorum a livello di pool. Se il numero di server in uso scende al di sotto del livello di funzionalità, come illustrato nella tabella seguente, i server rimanenti del pool arrestano tutti i servizi di Skype for Business Server. Tieni presente che i numeri della tabella seguente presuppongono che i server back-end del pool siano in funzione.
  
|Numero totale di server front-end nel pool  <br/> |Numero di server che devono essere in uso per il pool per essere funzionali  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3-4  <br/> |Qualsiasi 2  <br/> |
|5-6  <br/> |Qualsiasi 3  <br/> |
|7  <br/> |Qualsiasi 4  <br/> |
|8-9  <br/> |Qualsiasi 4 dei primi 7 Server  <br/> |
|10-12  <br/> |Qualsiasi 5 dei primi 9 server  <br/> |
   
Nella tabella precedente i "primi server" sono i server che sono stati allevati prima, cronologicamente, quando il pool è stato avviato per la prima volta. Per determinare questi server, puoi usare il `Get-CsComputer` cmdlet con l' `-PoolFqdn` opzione. Questo cmdlet visualizzerà i server nell'ordine in cui vengono visualizzati nella topologia e quelli nella parte superiore dell'elenco sono i primi server.
  
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Passaggi aggiuntivi per garantire la funzionalità dei pool

Per assicurarsi che i pool Front-End rimangano funzionali, è necessario guardare un paio di altri fattori.
  
- Quando si trasferiscono gli utenti al pool per la prima volta, assicurarsi che siano in esecuzione almeno tre server front-end.
    
- Se si stabilisce una relazione di associazione tra questo pool e un altro pool per scopi di ripristino di emergenza, dopo aver stabilito tale relazione, è necessario assicurarsi che il pool abbia tre server front-end in esecuzione contemporaneamente in modo da sincronizzare correttamente dati con il pool di backup. Per altre informazioni sulle caratteristiche di associazione e ripristino di emergenza del pool, vedere [pianificare l'elevata disponibilità e il ripristino di emergenza in Skype for Business Server](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Pool Front-end con due server front-end

Non è consigliabile distribuire un pool Front end che contiene solo due server front-end. Questa piccola piscina non fornirà una robusta soluzione ad alta disponibilità, ad esempio una piscina più grande, e richiederà cure aggiuntive per la gestione. Inoltre, se il server back-end di un pool a due server è andato in calo, anche l'intero pool potrebbe presto andare giù. Se si vogliono distribuire solo uno o due server con Skype for Business Server, è consigliabile distribuirli come server Standard Edition.
  
Se è necessario distribuire un pool con due server front-end, seguire queste linee guida:
  
- Se uno dei due server front-end scende, provare a riportare il server non riuscito al più presto possibile. Allo stesso modo, se è necessario aggiornare uno dei due server, riportarlo online non appena l'aggiornamento è terminato.
    
- Se per qualche motivo è necessario riportare entrambi i server contemporaneamente, eseguire le operazioni seguenti quando il tempo di inattività per il pool è terminato:
    
  - La procedura consigliata consiste nel riavviare entrambi i server front-end contemporaneamente. 
    
  - Se i due server non possono essere riavviati contemporaneamente, è consigliabile riportarli in ordine inverso rispetto all'ordine in cui sono stati ritirati.
    
  - Se non è possibile riportarli in questo ordine, usare il cmdlet seguente prima di riportare il pool:`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Errori e modifiche della configurazione del pool Front-End

Se un server front-end non riesce ed è improbabile che venga sostituito per alcuni giorni o più, rimuovere il server dalla topologia. Aggiungere il nuovo server front-end alla topologia quando è di nuovo disponibile.
  
Ogni volta che si apporta una modifica alla configurazione di un pool Front-End, ad esempio l'aggiunta o la rimozione di server, è necessario seguire queste linee guida:
  
- Dopo la pubblicazione della nuova topologia, è necessario riavviare ogni server front-end nel pool. Riavviare uno alla volta.
    
- Se l'intero pool è stato premuto durante la modifica della configurazione, eseguire il cmdlet seguente dopo la pubblicazione della nuova topologia:`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

