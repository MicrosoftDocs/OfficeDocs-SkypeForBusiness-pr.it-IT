---
title: Esperienza utente durante un errore del pool in Skype for Business Server
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
ms.assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
description: Informazioni sugli utenti che si verificano quando un pool Front End ha esito negativo o ha esito negativo durante il ripristino di emergenza in Skype for Business Server.
ms.openlocfilehash: 137ad9076febccb272e88e457ee56e6474cff107
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809906"
---
# <a name="user-experience-during-pool-failure-in-skype-for-business-server"></a>Esperienza utente durante un errore del pool in Skype for Business Server
 
Informazioni sugli utenti che si verificano quando un pool Front End ha esito negativo o ha esito negativo durante il ripristino di emergenza in Skype for Business Server.
  
Se non è possibile eseguire il failover di un pool, tutti gli utenti nel pool in questione devono disconnettersi e quindi accedere al pool di backup. Per un breve periodo di tempo, gli utenti che si connettono al pool di backup possono trovarsi in modalità Resilienza. In modalità di resilienza, gli utenti non sono in grado di eseguire attività che causerebbero una modifica permanente su Skype for Business Server, ad esempio l'aggiunta di un contatto. Al termine del failover, tutti gli utenti possono ottenere tutti i servizi dal pool di backup.
  
Tutte le chiamate, le riunioni o le conversazioni che un utente ha quando il pool ha esito negativo sono interrotte e l'utente deve ristabilire tali sessioni dopo il failover per continuare.
  
Gli utenti non vengono ricollocati durante il failover o il failback. Gli utenti che si trovano in un pool su cui si verifica un problema verranno infatti serviti temporaneamente dal pool di backup. Quando il pool Home viene ripristinato, l'amministratore può eseguire il failback degli utenti affinché vengano serviti dal pool originale, in cui sono ancora ospitati.
  
Si noti che il database del server di informazioni percorso non viene replicato nel pool di backup. Come procedura consigliata, l'amministratore dovrebbe eseguire con regolarità il backup del database LIS e utilizzare la copia di backup più recente per ripristinare tale database nel pool di backup dopo il failover.
  
## <a name="user-experience-during-failover"></a>Esperienza utente durante il failover

Quando un utente si trova in un pool che ha esito negativo, l'utente è disconnesso. Qualsiasi sessione peer-to-peer a cui ha partecipato l'utente è terminata, così come le conferenze organizzate dall'utente. L'utente non può riconnettersi finché non scade il timer di resilienza della funzione di registrazione o finché l'amministratore non avvia le procedure di failover, a seconda di quale di questi eventi avviene per primo. Quando l'utente si riconnette, si riconnetterà al pool di backup. Se si connette prima che il failover sia stato completato, sarà in modalità Resilienza fino al completamento del failover. Solo allora un utente può stabilire nuove sessioni o ristabilire le sessioni precedenti.
  
## <a name="user-experience-during-failback"></a>Esperienza utente durante il failback

Il failback del pool può verificarsi quando un utente in questione è connesso al pool di backup e l'utente rimane connesso e funziona durante il failback. Tenere presente che il processo di failback richiede alcuni minuti per il completamento. A titolo di riferimento, sono previsti fino a 60 minuti per un pool di 20.000 utenti.
  
Nelle tabelle riportate di seguito vengono illustrati ulteriori dettagli sul modo in cui un utente viene influenzato durante e dopo il failback, nonché su come gli utenti in altri pool visualizzano e interagiscono con un utente in un pool di cui viene eseguito il failover. 
  
Con il termine utente interessato viene indicato qualsiasi utente di cui sia stato eseguito il failover dal pool principale e che venga servito dal pool di backup. Un utente originariamente ospitato nel pool di backup non è un utente influenzato.
  
**Esperienza utente per un utente interessato in un pool in corso di failback**

|**Stato o attività dell'utente**|**Durante il failback**|**Dopo il completamento del failback**|
|:-----|:-----|:-----|
|Utente già connesso  <br/> |L'utente resta connesso al pool di backup. A un certo punto l'utente verrà disconnesso e riconnesso al pool principale originale, in modalità Resilienza.  <br/> |L'utente rimane connesso e passa alla modalità normale.  <br/> |
|Nuova connessione dell'utente  <br/> |L'utente può connettersi al pool principale in modalità Resilienza.  <br/> |L'utente può connettersi al pool principale originale in modalità normale.  <br/> |
|Conferenze in corso organizzate dall'utente interessato  <br/> |Tutte le modalità di conferenza vengono terminate. Viene visualizzato il pulsante Torna a partecipare, ma nessun utente può ripartecipare alla conferenza mentre l'utente interessato è in modalità Resilienza.  <br/> |Tutte le modalità ora funzionano. Tutti i partecipanti devono fare clic sul pulsante per tornare a partecipare alla conferenza.  <br/> |
|Conferenze in corso organizzate da un utente non interessato  <br/> |La conferenza prosegue e l'utente interessato può continuare a parteciparvi, ma può eseguire esclusivamente le operazioni consentite in modalità Resilienza.  <br/> |La conferenza prosegue e l'utente interessato può continuare a parteciparvi. Tutte le modalità funzionano dopo che l'utente esce dalla modalità Resilienza.  <br/> |
|Pianificazione o modifica delle riunioni pianificate, creazione di conferenze ad hoc  <br/> |Attività impossibili mentre l'utente è in modalità Resilienza.  <br/> |Attività disponibili per tutte le modalità.  <br/> |
|Presenza come viene visualizzata da altri utenti dello stesso pool  <br/> |Presenza sconosciuta mentre l'utente è connesso al pool di backup in modalità Resilienza.  <br/> |Viene visualizzato l'ultimo stato di presenza impostato dall'utente. Le eventuali variazioni di tale stato ora saranno visibili.  <br/> |
|Disponibilità dell'Elenco contatti e del Servizio Rubrica  <br/> |Non disponibili  <br/> |Disponibili  <br/> |
|Tutte le sessioni peer-to-peer e tutte le modalità  <br/> |Disponibili  <br/> |Disponibili  <br/> |
   
**Esperienza utente di un utente che si trova in un pool non interessato durante il failback di un altro pool**

|**Attività utente**|**Durante il failback**|**Dopo il completamento del failback**|
|:-----|:-----|:-----|
|Visualizzazione della presenza dell'utente interessato  <br/> |Viene visualizzato l'ultimo stato di presenza impostato dall'utente interessato.  <br/> |Funzionante. Gli utenti non interessati vedono le modifiche apportate dagli utenti interessati.  <br/> |
|Conferenze in corso organizzate dall'utente interessato  <br/> |Tutte le modalità di conferenza vengono terminate.  <br/> |Tutte le modalità ora funzionano. Tutti i partecipanti devono fare clic sul pulsante per tornare a partecipare alla conferenza.  <br/> |
|Conferenze in corso organizzate da un utente non interessato  <br/> |La conferenza prosegue e l'utente interessato può continuare a parteciparvi. Tutte le modalità funzionano.  <br/> |La conferenza prosegue e l'utente interessato può continuare a parteciparvi. Tutte le modalità funzionano.  <br/> |
|Tutte le sessioni peer-to-peer e tutte le modalità  <br/> |Disponibili  <br/> |Disponibili  <br/> |
   

