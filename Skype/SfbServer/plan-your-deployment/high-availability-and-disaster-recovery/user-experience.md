---
title: Esperienza utente durante l'errore del pool in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
description: Informazioni sugli utenti che si verificano quando un pool Front-end non supera o non riesce a eseguire il ripristino di emergenza in Skype for Business Server.
ms.openlocfilehash: 892601267f897050cff635d4d87bb4270e2e0e83
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802326"
---
# <a name="user-experience-during-pool-failure-in-skype-for-business-server"></a>Esperienza utente durante l'errore del pool in Skype for Business Server
 
Informazioni sugli utenti che si verificano quando un pool Front-end non supera o non riesce a eseguire il ripristino di emergenza in Skype for Business Server.
  
Se non è possibile eseguire il failover di un pool, tutti gli utenti del pool interessato saranno costretti a disconnettersi e quindi a eseguire l'accesso al pool di backup. Per un breve periodo gli utenti che accedono al pool di backup potrebbero essere in modalità resilienza. In modalità resilienza gli utenti non possono eseguire attività che causerebbero una modifica persistente in Skype for Business Server, ad esempio l'aggiunta di un contatto. Al termine del failover, tutti gli utenti possono ottenere tutti i servizi dal pool di backup.
  
Tutte le chiamate, le riunioni o le conversazioni che un utente ha quando il pool non riesce vengono interrotte e l'utente deve ristabilire tali sessioni dopo il failover per continuare.
  
Gli utenti non vengono reospitati durante il failover o il failback. Gli utenti ospitati in un pool che non riesce verranno temporaneamente serviti dal pool di backup. Quando il pool Home viene ripristinato, l'amministratore può non restituire questi utenti per essere serviti dal pool originale, dove sono ancora ospitati.
  
Tieni presente che il database del server delle informazioni sulla posizione non viene replicato nel pool di backup. Per le procedure consigliate, l'amministratore deve eseguire regolarmente il backup del database LIS e usare la copia di backup più recente per ripristinare il database LIS nel pool di backup dopo il failover.
  
## <a name="user-experience-during-failover"></a>Esperienza utente durante il failover

Quando un utente si trova in un pool che non riesce, l'utente viene disconnesso. Qualsiasi sessione peer-to-peer a cui l'utente ha partecipato è terminata, così come le conferenze organizzate dall'utente. L'utente non può eseguire l'accesso finché non scade il timer di resilienza del registrar o l'amministratore avvia procedure di failover, a seconda di quale verrà prima. Quando l'utente esegue il log-in, eseguirà l'accesso al pool di backup. Se l'accesso è avvenuto prima del completamento del failover, sarà in modalità resilienza fino al completamento del failover. Solo allora un utente può stabilire nuove sessioni o ristabilire le sessioni precedenti.
  
## <a name="user-experience-during-failback"></a>Esperienza utente durante il failback

Il failback del pool può verificarsi mentre un utente interessato ha effettuato l'accesso al pool di backup e l'utente rimane connesso e sta lavorando durante il failback. Tieni presente che il processo di failback richiede diversi minuti per il completamento. Per riferimento, si prevede di richiedere fino a 60 minuti per un pool di utenti di 20.000.
  
Nelle tabelle seguenti sono illustrati altri dettagli sul modo in cui un utente è interessato durante e dopo il failback, nonché sul modo in cui gli utenti di altri pool possono vedere e interagire con un utente in un pool di cui non è stato eseguito il failover. 
  
Il termine utente interessato si riferisce a qualsiasi utente che non ha eseguito il failover dal pool Home e viene gestito dal pool di backup. Un utente originariamente ospitato nel pool di backup non è un utente interessato.
  
**Esperienza utente per un utente interessato in un pool in failback**

|**Stato utente o attività**|**Durante il failback**|**Dopo il completamento del failback**|
|:-----|:-----|:-----|
|Stato utente dell'utente già connesso  <br/> |L'utente rimane connesso e collegato al pool di backup. Ad un certo punto l'utente verrà disconnesso e si riaccederà al pool di Home originale, in modalità resilienza.  <br/> |L'utente rimane connesso e passa alla modalità normale.  <br/> |
|Registrazione di un nuovo utente  <br/> |L'utente può accedere al pool Home in modalità resilienza.  <br/> |L'utente può accedere al pool di Home originale in modalità normale.  <br/> |
|Conferenze in corso organizzate da un utente interessato  <br/> |Tutte le modalità di conferenza vengono terminate. Viene visualizzato il pulsante Riunisci, ma non è possibile partecipare alla riunione quando l'utente interessato è in modalità di resilienza.  <br/> |Tutte le modalità funzionano ora. Ogni partecipante deve fare clic per tornare a partecipare alla conferenza.  <br/> |
|Conferenze in corso organizzate da un utente non interessato  <br/> |La conferenza continua e l'utente interessato può rimanere nella conferenza. L'utente interessato si limita a ciò che può fare in modalità resilienza.  <br/> |La conferenza continua e l'utente interessato può rimanere in conferenza e tutte le modalità funzionano dopo l'uscita dalla modalità resilienza.  <br/> |
|Pianificazione o modifica delle riunioni pianificate, creazione di conferenze ad hoc  <br/> |Non è possibile mentre l'utente è in modalità di resilienza.  <br/> |Disponibile per tutte le modalità.  <br/> |
|Presenza visualizzata da altri utenti nello stesso pool  <br/> |Presenza sconosciuta mentre l'utente ha eseguito l'accesso al pool di backup durante la modalità resilienza.  <br/> |Mostra lo stato dell'ultima presenza impostato dall'utente e le modifiche alla presenza verranno riflesse.  <br/> |
|Disponibilità del servizio elenco contatti e Rubrica  <br/> |Non disponibile  <br/> |Disponibili  <br/> |
|Tutte le sessioni e le modalità peer-to-peer  <br/> |Disponibili  <br/> |Disponibili  <br/> |
   
**Esperienza utente per un utente ospitato in un pool non interessato durante il failback di un altro pool**

|**Attività utente**|**Durante il failback**|**Dopo il completamento del failback**|
|:-----|:-----|:-----|
|Visualizzazione della presenza dell'utente interessato  <br/> |Mostra lo stato dell'ultima presenza impostato dall'utente interessato.  <br/> |Uso. Gli utenti inalterati vedono gli aggiornamenti apportati dagli utenti interessati.  <br/> |
|Conferenze in corso organizzate da un utente interessato  <br/> |Tutte le modalità di conferenza vengono terminate.  <br/> |Tutte le modalità funzionano ora. Ogni partecipante deve fare clic per tornare a partecipare alla conferenza.  <br/> |
|Conferenze in corso organizzate da un utente non interessato  <br/> |La conferenza continua e l'utente interessato può rimanere in conferenza e tutte le modalità funzionano.  <br/> |La conferenza continua e l'utente interessato può rimanere in conferenza e tutte le modalità funzionano.  <br/> |
|Tutte le sessioni e le modalità peer-to-peer  <br/> |Disponibili  <br/> |Disponibili  <br/> |
   

