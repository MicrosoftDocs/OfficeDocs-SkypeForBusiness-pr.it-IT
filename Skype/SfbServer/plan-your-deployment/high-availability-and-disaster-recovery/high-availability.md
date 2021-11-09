---
title: Disponibilità e gestione elevata del pool Front End
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: Informazioni sulla gestione dei pool Front End in Skype for Business Server, tra cui la gestione dei pool, la perdita di quorum e i passaggi speciali per i pool con solo due Front End Server.
ms.openlocfilehash: f8ad22c7728fc4fb62980a81fa659558aaba4be7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60831850"
---
# <a name="front-end-pool-high-availability-and-management"></a>Disponibilità e gestione elevata del pool Front End
 
Informazioni sulla gestione dei pool Front End in Skype for Business Server, tra cui la gestione dei pool, la perdita di quorum e i passaggi speciali per i pool con solo due Front End Server.
  
In Skype for Business Server, l'architettura dei pool Front End utilizza un modello di sistemi distribuiti, con i dati di ogni utente conservati su fino a tre Front End Server nel pool. È consigliabile che tutti edizione Enterprise pool Front End includano almeno tre Front End Server.

> [!NOTE]
> Skype for Business Server 2019 non supporta edizione Enterprise pool Front End con due Front End Server e non consente la pubblicazione della topologia in tale scenario.
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Pianificazione della gestione dei pool Front End

 Skype for Business Server viene utilizzato un modello di sistemi distribuiti basato su Windows Fabric. In questo modello, i dati importanti per ogni utente e conferenza vengono archiviati in tre Front End Server in un pool Front End. Questi tre server che archiviano un determinato set di dati sono denominatireplica.
  
Con il modello distribuito per i pool Front End, un determinato numero di server di un pool deve essere in esecuzione per il funzionamento del pool. Esistono due modalità di perdita per un pool.
  
- Perdita del quorum a livello di gruppo di routing causata da un numero insufficiente di server di replica per un gruppo di routing specifico. Un gruppo di routing è un insieme di utenti ospitati nel pool. Ogni gruppo di routing dispone di tre repliche nel pool: una replica primaria e due repliche secondarie.
    
- Perdita di quorum a livello di pool, causata quando nel pool non è in esecuzione un numero sufficiente di server di seed. 
    
### <a name="routing-group-level-quorum-loss"></a>Perdita quorum a livello di gruppo di routing

La prima volta che si avvia un nuovo pool Front End, è essenziale che l'85% dei server sia operativo, come illustrato nella tabella seguente. Se sono in esecuzione meno server, è possibile che i servizi siano bloccati nello stato iniziale e che il pool non venga avviato.
  
|Numero totale di server nel pool  <br/> |Numero di server che devono essere in esecuzione per il primo avvio del pool  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3   <br/> |3   <br/> |
|4   <br/> |3   <br/> |
|5  <br/> |4   <br/> |
|6   <br/> |5  <br/> |
|7   <br/> |5  <br/> |
|8   <br/> |6   <br/> |
|9   <br/> |7   <br/> |
|10   <br/> |8   <br/> |
|11   <br/> |9   <br/> |
|12   <br/> |10   <br/> |
|16 **Per Skype for Business Server 2019** <br/> |12   <br/> |


   
Ogni volta che il pool viene avviato successivamente, deve essere avviato l'85% dei server (come illustrato nella tabella precedente). Se non è possibile avviare questo numero di server , ma è possibile avviare un numero sufficiente di server in modo da non essere a livello di quorum a livello di pool, è possibile utilizzare il cmdlet per consentire al pool di eseguire il ripristino dalla perdita del quorum a livello di gruppo di routing e fare  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` progressi. Per ulteriori informazioni su come utilizzare questo cmdlet, vedere [Reset-CsPoolRegistrarState.](/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps) 
  
> [!NOTE]
> Nei pool con un numero pari di server, Skype for Business Server il database di SQL primario come server di controllo. In un pool come questo, se si arresta il database primario e si passa alla copia mirror e si arresta un numero sufficiente di Front End Server in modo che l'esecuzione non sia sufficiente in base alla tabella precedente, l'intero pool verrà arrestato. Per ulteriori informazioni, vedere [Database Mirroring Witness](/sql/database-engine/database-mirroring/database-mirroring-witness). 
  
#### <a name="pool-level-quorum-loss"></a>Perdita quorum a livello di pool

Per il funzionamento di un pool Front End, non può essere in caso di perdita del quorum a livello di pool. Se il numero di server in esecuzione scende al di sotto del livello funzionale, come illustrato nella tabella seguente, i server rimanenti nel pool arresteranno tutti Skype for Business Server servizi. Si noti che i numeri nella tabella seguente presuppongono che i server back-end nel pool siano in esecuzione.
  
|Numero totale di Front End Server nel pool  <br/> |Numero minimo di server attivi per il funzionamento del pool  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3-4  <br/> |Qualsiasi 2  <br/> |
|5-6  <br/> |Qualsiasi 3  <br/> |
|7   <br/> |Qualsiasi 4  <br/> |
|8-9  <br/> |Qualsiasi 4 dei primi 7 server  <br/> |
|10-12  <br/> |Qualsiasi 5 dei primi 9 server  <br/> |
|12-16 **Per Skype for Business Server 2019**  <br/> |Qualsiasi 7 dei primi 12 server  <br/> |
   
Nella tabella precedente, i "primi server" sono i server che sono stati avviati per primi, cronologicamente, quando il pool è stato avviato per la prima volta. Per determinare questi server, è possibile utilizzare il  `Get-CsComputer` cmdlet con `-PoolFqdn` l'opzione . Questo cmdlet mostrerà i server nell'ordine in cui sono visualizzati nella topologia e quelli all'inizio dell'elenco sono i primi server.
  
> [!IMPORTANT]
> Il numero massimo di server front-end è stato aumentato a 16 in [Skype for Business Server 2019](../../../SfBServer2019/plan/user-model-2019.md)
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Passaggi aggiuntivi per garantire che i pool siano funzionali

È consigliabile osservare un paio di altri fattori per garantire che i pool Front End rimangano funzionanti.
  
- Quando si spostano gli utenti nel pool per la prima volta, assicurarsi che siano in esecuzione almeno tre Front End Server.
    
- Se si stabilisce una relazione di associazione tra il pool e un altro pool a scopo di ripristino di emergenza, dopo aver stabilito tale relazione è necessario verificare che nel pool siano in esecuzione contemporaneamente tre Front End Server per sincronizzare correttamente i dati con il pool di backup. Per ulteriori informazioni sulle funzionalità di associazione del pool e ripristino di emergenza, vedere [Plan for high availability and disaster recovery in Skype for Business Server](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Pool Front End con due Front End Server

Non è consigliabile distribuire un pool Front End contenente due soli Front End Server. Questo pool di piccole dimensioni non fornirà una soluzione affidabile a disponibilità elevata come farebbe un pool più grande e necessita di ulteriore attenzione nella gestione. Inoltre, se il server back-end di un pool a due server si è arrestato, è probabile che presto anche l'intero pool si insedierà. Se si desidera distribuire solo uno o due server che eseguono Skype for Business Server, è consigliabile distribuirli come edizione Standard server.
  
Se è necessario distribuire un pool con due Front End Server, attenersi alle linee guida seguenti:
  
- Se uno dei due Front End Server si arresta, riattivarlo al più presto. Analogamente, se occorre aggiornare uno dei due server, riportarlo online subito dopo l'aggiornamento.
    
- Se per qualche ragione si rende necessario arrestare entrambi i server contemporaneamente, al termine dell'intervento procedere come segue:
    
  - La procedura consigliata consiste nel riavviare entrambi i Front End Server contemporaneamente. 
    
  - Se non è possibile riavviare entrambi i server contemporaneamente, riattivarli in ordine inverso rispetto a quello di arresto.
    
  - Se non è possibile riportarli nell'ordine indicato, utilizzare il cmdlet seguente prima di eseguire il backup del pool:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Errori e modifiche alla configurazione del pool Front End

Se un front-end server ha esito negativo e non può essere sostituito per alcuni giorni o più, rimuovere il server dalla topologia. Aggiungere il nuovo Front End Server alla topologia quando sarà di nuovo disponibile.
  
Ogni volta che si apporta una modifica di configurazione a un pool Front End, ad esempio aggiungendo o rimuovendo server, è necessario attenersi alle linee guida seguenti:
  
- Dopo aver pubblicato la nuova topologia, è necessario riavviare ogni Front End Server del pool. Riavviarli uno alla volta.
    
- Se l'intero pool è stato arrestato durante la modifica della configurazione, eseguire il cmdlet seguente dopo la pubblicazione della nuova topologia:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
