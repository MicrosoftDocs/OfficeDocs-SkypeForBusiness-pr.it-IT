---
title: Pianificazione della capacità per il server Chat persistente Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
description: 'Riepilogo: leggere questo argomento per informazioni sulla pianificazione della capacità per il server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 4b84d06a7b6c7f20f26d22ed5718da9abf8108d9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834062"
---
# <a name="capacity-planning-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Pianificazione della capacità per il server Chat persistente Skype for Business Server 2015
 
**Riepilogo:** Leggere questo argomento per informazioni sulla pianificazione della capacità per il server Chat persistente in Skype for Business Server 2015.
  
Il server Chat persistente può eseguire chat multi-utente in tempo reale che possono persistere per il recupero e la ricerca futuri. A differenza della messaggistica istantanea di gruppo salvata nella cassetta postale di un utente se è configurata la cronologia delle conversazioni, una sessione del server Chat persistente rimane aperta più a lungo e il contenuto viene salvato su un server, insieme ai messaggi, ai file, agli URL e ad altri dati che fanno parte di una conversazione in corso.
  
La pianificazione della capacità è una parte importante della preparazione alla distribuzione del server Chat persistente. In questo argomento vengono fornite tabelle di pianificazione della capacità che è possibile utilizzare per determinare la configurazione ottimale per la distribuzione. Viene inoltre descritto come gestire al meglio le distribuzioni del server Chat persistente che richiedono una maggiore capacità nelle ore di punta.
  
Prima di leggere questa sezione, è necessario avere familiarità con le topologie di Persistent Chat. Per ulteriori informazioni, vedere [Plan Persistent Chat Server topology](topology.md).

> [!NOTE] 
> La chat persistente è disponibile Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in Teams. Per ulteriori informazioni, vedere [Introduzione all'Microsoft Teams aggiornamento.](/microsoftteams/upgrade-start-here) Se è necessario utilizzare persistent chat, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità Teams o continuare a usare Skype for Business Server 2015. 
  
## <a name="persistent-chat-server-capacity-planning"></a>Pianificazione della capacità del server Chat persistente

Le tabelle seguenti consentono di pianificare la capacità per il server Chat persistente modellando il modo in cui varie impostazioni del server Chat persistente influiscono sulla capacità.
  
- Pianificare la capacità per il numero di utenti
    
- Pianificare la capacità per l'accesso alle chat room
    
- Pianificare la capacità per l'accesso alle chat room tramite invito
    
- Pianificare la capacità per le prestazioni
    
### <a name="plan-capacity-for-number-of-users-for-persistent-chat-server"></a>Pianificare la capacità per il numero di utenti per il server Chat persistente

Utilizzare la tabella di esempio seguente per determinare il numero di utenti che sarà possibile supportare.
  
**Esempio di capacità massima del pool di server Chat persistente**

- Istanze del servizio Chat persistente attive: 4  <br/> 
- Istanze del servizio Persistent Chat: 8 (un massimo di 4 può essere attivo; 4 devono essere inattive)  <br/>
- Utenti attivi connessi: 80.000  <br/>
- Totale utenti di cui è stato eseguito il provisioning: 150.000  <br/>
- Numero di endpoint: 120.000  <br/>
   
Nell'esempio precedente, il piano prevede il supporto del numero massimo di utenti consentito dal server Chat persistente: quattro server/istanze del servizio Chat persistente (possono avere altri quattro server passivi che eseguono il server Chat persistente per la disponibilità elevata e il ripristino di emergenza) e 20.000 utenti per server, per un totale di 80.000 utenti attivi.
  
### <a name="plan-capacity-for-chat-room-access"></a>Pianificare la capacità per l'accesso alle chat room

La tabella di esempio seguente consente di pianificare la gestione dell'accesso alle chat room in un pool di server Chat persistente.
  
**Esempio di gestione dell'accesso alle chat room**

|&nbsp;|Chat room di piccole dimensioni|Chat di medie dimensioni|Chat room di grandi dimensioni|Totale|
|:-----|:-----|:-----|:-----|:-----|
|Dimensioni delle chat room (numero di utenti connessi)   |30 per sala   |150 per camera   |16.000 per camera   ||
|Chat   |32,000   |1,067   |10    |33,077   |
|% di sale auditorium   |1%   |1%   |50%   ||
|% di sale aperte   |3%   |3%   |50%   ||
|Sale aperte (nessuna appartenenza esplicita)   |960   |32   |5   |997   |
|Sale non aperte (sale regolari con appartenenza esplicita)   |31,040   |1.035   |5   |32,080   |
|Sale auditorium (voce relatori aggiuntivi)   |0   |32   |5   ||
|Sale gestite dall'appartenenza diretta   |50%   |10%   |0%   ||
|Chat gestite per gruppi di utenti   |50%   |90%   |100%   ||
|Gruppi di utenti nell'elenco di appartenenze di ogni chat room per le sale aperte (non specificato esplicitamente)   |0   |0   |0   ||
|Utenti nell'elenco di appartenenze di ogni chat room per le chat non aperte   |30   |150   |16,000   ||
|Gruppi di utenti nell'elenco di appartenenze di ogni chat room per le chat non aperte   |3    |5   |10    ||
|Utenti e gruppi di utenti nell'elenco dei manager di ogni chat room (per sale aperte e non aperte)   |6    |6    |6    ||
|Utenti e gruppi di utenti in ogni elenco di relatori di chat auditorium (per sale aperte e non aperte)   |6    |6    |6    ||
|Entità di appartenenza basata sull'utente in tutte le sale non aperte   |465,600   |15,520   |-   ||
|Entità di appartenenza basata su gruppi di utenti in tutte le sale non aperte   |46,560   |4656   |50   ||
|Entità basate su utenti e gruppi di utenti in tutte le chat room auditorium   |0   |192   |50   ||
|Entità manager basate su utenti e gruppi di utenti in tutti gli elenchi dei manager delle chat room   |192,000   |6,400   |60   ||
|Utenti attivi per chat   |30   |150   |16,000   ||
|Chat per utente   |12    |2   |2   |16    |
|Gruppi di utenti nell'elenco di appartenenze di ogni chat room   |10    |10    |15    ||
|Chat gestite per gruppi di utenti   |50%   |50%   |50%   ||
|Entità di appartenenza basata sui gruppi di utenti in tutte le chat   |155,200   |5173   |68   ||
|Entità di appartenenza basata sugli utenti in tutte le chat   |465,600   |77,600   |72,000   ||
|Utenti e gruppi di utenti in ogni elenco dei gestori delle chat, dei relatori delle chat e degli ambiti   |6    |6    |6    ||
|Utenti e gruppi di utenti in tutti gli elenchi di gestione, relatore e ambito di tutte le chat room   |192,000   |6400   |60   ||
|Voci di controllo di accesso   |704,160   |26,768   |160   |731,088   |
|Voci di controllo di accesso massime   ||||2,000,000   |
   
Nell'esempio precedente, quando si distribuiscono i server Chat persistente in base alle linee guida consigliate, possono gestire fino a 80.000 utenti attivi in un pool a quattro server con la conformità abilitata.
  
Questo esempio mostra le chat room classificate come piccole (30 utenti attivi in un determinato momento), medie (150 utenti attivi) e grandi (16.000 utenti attivi). Il numero supportato di chat room di una determinata dimensione nella tabella precedente viene calcolato in base al numero totale di:
  
- Utenti attivi nel sistema
    
- Utenti attivi nelle chat delle dimensioni specificate
    
- Chat delle dimensioni specificate cui partecipa ogni singole utente
    
Per ogni chat room, la tabella di pianificazione della capacità precedente specifica il numero di voci di controllo di accesso associate alla chat room, incluse le voci assegnate direttamente alla chat room. È possibile controllare l'accesso a singole chat tramite elenchi di controllo di accesso. È inoltre possibile controllare l'accesso a livello di categoria. In un ACL, una singola voce di controllo di accesso può essere un gruppo di utenti, ad esempio un gruppo di sicurezza, una lista di distribuzione o un singolo utente. È possibile definire voci di controllo di accesso per gestori, relatori e membri delle chat.
  
> [!IMPORTANT]
> Nella pianificazione della strategia per la gestione delle chat room, tenere presente che il numero totale di voci di controllo di accesso consentite è 2 milioni. Se le voci di controllo di accesso calcolate superano i 2 milioni, le prestazioni del server potrebbero peggiorare in modo significativo. Per evitare questo problema, quando possibile, assicurarsi che le voci di controllo di accesso siano gruppi di utenti anziché singoli utenti. 
  
### <a name="plan-capacity-for-managing-chat-room-access-by-invitation"></a>Pianificare la capacità per la gestione dell'accesso alle chat room tramite invito

È possibile utilizzare la seguente tabella di pianificazione della capacità per comprendere il numero di inviti creati e archiviati dal server Chat persistente nel database di Persistent Chat quando è configurato per l'invio di inviti. È possibile gestire gli inviti  nella categoria utilizzando la pagina Impostazioni categoria chat room nel Pannello di controllo di Skype for Business Server oppure utilizzando il cmdlet **Windows PowerShell, set-csPersistentChatCategory.** È possibile gestire gli inviti in una chat room (in  linea con quanto la categoria consente) utilizzando la pagina Gestione chat avviata dal client Skype for Business oppure utilizzando un cmdlet di **Windows PowerShell, set-csPersistentChatRoom.**
  
I dati di esempio nella tabella seguente presuppongono che nella pagina **Impostazioni**  chat room per il 50% di tutte le chat room l'opzione Inviti sia impostata su **Sì.**
  
> [!IMPORTANT]
> Se il valore calcolato per il numero di inviti generati dal server supera 1 milione, le prestazioni del server potrebbero peggiorare in modo significativo. Per evitare questo problema, assicurarsi di ridurre al minimo il numero di chat room configurate per inviare inviti o limitare il numero di utenti che possono partecipare alle chat room configurate per l'invio di inviti. 
  
**Esempio di accesso alle chat room tramite invito**

|&nbsp;|Chat room di piccole dimensioni|Chat di medie dimensioni|Chat room di grandi dimensioni|Totale|
|:-----|:-----|:-----|:-----|:-----|
|Utenti che possono accedere alla chat room   |30 per sala   |150 per camera   |16.000 per camera   ||
|Percentuale di sale con inviti   |50%   |50%   |50%   ||
|Chat configurate per l'invio di inviti   |16,000   |533   |5   ||
|Utenti che possono accedere alla chat   |60   |225   |16,000   ||
|Inviti generati dal server Chat persistente   |960,000   |120,000   |80,000   |1,160,000   |
|Numero massimo consentito di inviti   ||||2,000,000   |
|Modello 1 - Iniziare con il numero previsto di messaggi per sala al giorno   |||||
|Frequenza chat per sala (al giorno)   |50   |500   |100   |650   |
|Frequenza chat (al secondo) in tutte le chat room   |55.56   |18.52   |0.03   |74   |
|Modello 2 - Iniziare con il numero di messaggi pubblicati per utente al giorno   |||||
|Frequenza chat per utente al giorno   |15    |5   |0.1   |20   |
|Frequenza chat per sala (al giorno)   |38   |375   |800   |1,213   |
|Frequenza chat (al secondo) in tutte le chat room   |41.67   |13.89   |0.28   |56   |
   
### <a name="plan-capacity-for-persistent-chat-server-performance"></a>Pianificare la capacità per le prestazioni del server Chat persistente

Nella tabella seguente viene descritto il modello utente per il server Chat persistente. Fornisce la base per i requisiti di pianificazione della capacità e rappresenta un'organizzazione tipica con 80.000 utenti simultanei su quattro server.
  
**Modello utente per le prestazioni del server Chat persistente**

- Numero di utenti attivi connessi: 80.000  <br/>
- Numero di istanze del servizio Server Chat persistente: 4  <br/>
- Dimensioni delle chat room di piccole dimensioni: 30 utenti  <br/> 
- Dimensioni delle chat room medie: 150 utenti  <br/>
- Dimensioni delle chat room di grandi dimensioni: 16.000 utenti  <br/>
- Numero totale di chat room: 33.077  <br/> 
- Numero di chat di piccole dimensioni: 32.000  <br/> 
- Numero di chat di medie dimensioni: 1.067  <br/> 
- Numero di chat di grandi dimensioni: 10  <br/> 
- Numero totale di chat room per utente: 16  <br/> 
- Numero di chat di piccole dimensioni per utente: 12  <br/> 
- Numero di chat di medie dimensioni per utente: 2  <br/> 
- Numero di chat di grandi dimensioni per utente: 2  <br/> 
- Numero di chat room unite per utente: 24  <br/>
- Frequenza di join di picco: 10/secondo  <br/> 
- Frequenza chat totale: 24/secondo  <br/> 
- Frequenza di chat per chat di piccole dimensioni: 22,22/secondo  <br/> 
- Frequenza chat per chat di medie dimensioni: 1,67/secondo  <br/> 
- Frequenza di chat per chat di grandi dimensioni: ~0,15/secondo  <br/> 
- Percentuale di chat room configurate per gli inviti: 50%  <br/>
- Percentuale di appartenenze dirette: 50%  <br/>
- Percentuale di appartenenze ai gruppi: 50%  <br/> 
- Numero medio di affiliazioni predecessore in Servizi di dominio Active Directory: 100 - 200  <br/>
- Numero di contatti sottoscritti per utente: 80  <br/> 
- Numero medio di endpoint per utente: 1,5  <br/> 
- Numero medio di chat visibili per endpoint: 1,5  <br/> 
- Numero medio di chat visibili per utente: 2,25 (50% per 1 sala e 50% per 2 sale); Fino a 6 sale aperte, una per monitor  <br/> 
- Numero di partecipanti di cui è stato eseguito il polling per intervallo: 25 per chat room visibile  <br/> 
- Durata dell'intervallo di polling: 5 minuti  <br/> 
- Numero di partecipanti a cui è stato eseguito il polling al secondo: 15.000  <br/>
- Numero di modifiche di presenza all'ora per utente: 6  <br/> 
- Numero di modifiche di presenza al secondo: 133,33  
   

