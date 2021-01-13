---
title: Disponibilità elevata e gestione del pool Front End
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: Ulteriori informazioni sulla gestione del pool Front end in Skype for Business Server, tra cui la gestione di pool, la perdita di quorum e passaggi speciali per i pool con solo due front end server.
ms.openlocfilehash: 3f1924b7a8ad26b880f8674ada4f0c99a1bc4596
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802796"
---
# <a name="front-end-pool-high-availability-and-management"></a>Disponibilità elevata e gestione del pool Front End
 
Ulteriori informazioni sulla gestione del pool Front end in Skype for Business Server, tra cui la gestione di pool, la perdita di quorum e passaggi speciali per i pool con solo due front end server.
  
In Skype for Business Server, l'architettura dei pool Front end utilizza un modello di sistemi distribuiti, con i dati di ogni utente conservati su ben tre Front End Server nel pool. È consigliabile che tutti i pool Enterprise Edition front end includano almeno tre Front End Server.

> [!NOTE]
> Skype for Business Server 2019 non supporta pool Enterprise Edition front end con due front end server e non consentirà la pubblicazione della topologia in tale scenario.
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Pianificazione per la gestione dei pool Front End

 Skype for Business Server utilizza un modello di sistemi distribuiti basato su Windows Fabric. In questo modello, i dati importanti per ogni utente e conferenza sono archiviati in tre Front End Server in un pool Front end. Questi tre server che archiviano un determinato set di dati sono calledreplicas.
  
Con il modello distribuito per i pool Front End, è necessario che sia in esecuzione un determinato numero di server del pool per il funzionamento del pool. Sono disponibili due modalità di perdita per un pool.
  
- Perdita di quorum a livello di gruppo di routing, causata da server di replica non sufficienti per un gruppo di routing specifico. Un gruppo di routing è un insieme di utenti ospitati nel pool. Ogni gruppo di routing ha tre repliche nel pool: una replica primaria e due repliche secondarie.
    
- Perdita di quorum a livello di pool, causata quando i server di seeding non sono sufficienti in esecuzione nel pool. 
    
### <a name="routing-group-level-quorum-loss"></a>Perdita di quorum a livello di gruppo di routing

La prima volta che si avvia un nuovo pool Front End, è essenziale che il 85% dei server sia attivo e in esecuzione, come illustrato nella tabella seguente. Se sono in esecuzione meno server, è possibile che i servizi siano bloccati nello stato iniziale e che il pool non venga avviato.
  
|Numero totale di server nel pool  <br/> |Numero di server che devono essere in esecuzione per l'avvio del pool per la prima volta  <br/> |
|:-----|:-----|
|2   <br/> |1   <br/> |
|3   <br/> |3   <br/> |
|4   <br/> |3   <br/> |
|5   <br/> |4   <br/> |
|6   <br/> |5   <br/> |
|7   <br/> |5   <br/> |
|8   <br/> |6   <br/> |
|9   <br/> |7   <br/> |
|10   <br/> |8   <br/> |
|11   <br/> |9   <br/> |
|12   <br/> |10   <br/> |
|16 **per Skype for Business Server 2019** <br/> |12   <br/> |


   
Ogni volta che viene avviato il pool, 85% dei server devono essere avviati (come illustrato nella tabella precedente). Se non è possibile avviare questo numero di server, ma è possibile avviare server sufficienti in modo che non si trovino perdite di quorum a livello di pool, è possibile utilizzare il  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet per abilitare il ripristino del pool dalla perdita del quorum a livello di gruppo di routing e procedere. Per ulteriori informazioni sull'utilizzo di questo cmdlet, vedere [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps). 
  
> [!NOTE]
> In pool con un numero pari di server, Skype for Business Server utilizza il database SQL primario come testimone. In un pool di questo tipo, se si arresta il database primario e si passa alla copia del mirror e si arrestano i server front end sufficienti in modo che non siano sufficienti in esecuzione in base alla tabella precedente, l'intero pool passerà. Per ulteriori informazioni, vedere [database mirroring witness](https://go.microsoft.com/fwlink/?LinkId=393672). 
  
#### <a name="pool-level-quorum-loss"></a>Perdita di quorum a livello di pool

Affinché un pool Front end funzioni a tutti, non può essere in perdita di quorum a livello di pool. Se il numero di server in esecuzione scende al di sotto del livello di funzionalità, come illustrato nella tabella seguente, i server rimanenti del pool interromperanno tutti i servizi di Skype for Business Server. Si noti che i numeri nella tabella seguente presuppongono che i server back-end del pool siano in esecuzione.
  
|Numero totale di Front End Server nel pool  <br/> |Numero minimo di server attivi per il funzionamento del pool  <br/> |
|:-----|:-----|
|2   <br/> |1   <br/> |
|3-4  <br/> |Qualsiasi 2  <br/> |
|5-6  <br/> |Qualsiasi 3  <br/> |
|7   <br/> |Qualsiasi 4  <br/> |
|8-9  <br/> |Qualsiasi 4 dei primi 7 Server  <br/> |
|10-12  <br/> |Qualsiasi 5 dei primi 9 server  <br/> |
|12-16  **per Skype for Business Server 2019**  <br/> |Qualsiasi 7 dei primi 12 server  <br/> |
   
Nella tabella precedente, i "First Server" sono i server che sono stati portati in primo luogo, in ordine cronologico, quando il pool è stato avviato per la prima volta. Per determinare questi server, è possibile utilizzare il  `Get-CsComputer` cmdlet con l' `-PoolFqdn` opzione. Questo cmdlet mostrerà i server nell'ordine in cui vengono visualizzati nella topologia e quelli nella parte superiore dell'elenco sono i primi server.
  
> [!IMPORTANT]
> Il numero massimo di front end server è stato aumentato a 16 in [Skype for Business server 2019](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019)
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Passaggi aggiuntivi per garantire che i pool siano funzionali

È consigliabile guardare un paio di altri fattori per garantire che i pool Front End rimangano funzionali.
  
- Quando si spostano gli utenti nel pool per la prima volta, assicurarsi che siano in esecuzione almeno tre Front End Server.
    
- Se si stabilisce una relazione di accoppiamento tra il pool e un altro pool per scopi di ripristino di emergenza, dopo aver stabilito tale relazione è necessario assicurarsi che il pool disponga di tre Front End Server in esecuzione contemporaneamente per sincronizzare correttamente i dati con il pool di backup. Per ulteriori informazioni sulle funzionalità di abbinamento dei pool e ripristino di emergenza, vedere [pianificare la disponibilità elevata e il ripristino di emergenza in Skype for Business Server](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Pool Front end con due front end server

Non è consigliabile distribuire un pool Front End contenente due soli Front End Server. Questo piccolo pool non fornirà una soluzione a disponibilità elevata robusta come una piscina più grande e avrà bisogno di ulteriore assistenza nella gestione. Inoltre, se il server back-end di un pool con due server è diminuito, l'intero pool sarebbe probabile che si verifichino anche rapidamente. Se si desidera distribuire solo uno o due server che eseguono Skype for Business Server, è consigliabile distribuirli come server Standard Edition.
  
Se si ha mai bisogno di distribuire un pool con due front end server, seguire queste linee guida:
  
- Se uno dei due Front End Server si arresta, riattivarlo al più presto. Analogamente, se occorre aggiornare uno dei due server, riportarlo online subito dopo l'aggiornamento.
    
- Se per qualche ragione si rende necessario arrestare entrambi i server contemporaneamente, al termine dell'intervento procedere come segue:
    
  - La procedura consigliata consiste nel riavviare entrambi i front end server contemporaneamente. 
    
  - Se non è possibile riavviare entrambi i server contemporaneamente, riattivarli in ordine inverso rispetto a quello di arresto.
    
  - Se non è possibile eseguire il backup in tale ordine, utilizzare il cmdlet seguente prima di riportare il pool:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Errori e modifiche alla configurazione del pool Front End

Se un front end server ha esito negativo e non è probabile che venga sostituito per alcuni giorni o più, rimuovere il server dalla topologia. Aggiungere il nuovo front end server alla topologia quando è disponibile di nuovo.
  
Ogni volta che si apportano modifiche di configurazione a un pool Front End, ad esempio l'aggiunta o la rimozione di server, è necessario attenersi alle linee guida seguenti:
  
- Dopo la pubblicazione della nuova topologia, è necessario riavviare ogni Front End Server nel pool. Riavviarli uno alla volta.
    
- Se l'intero pool è stato premuto durante la modifica della configurazione, eseguire il cmdlet seguente dopo la pubblicazione della nuova topologia:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

