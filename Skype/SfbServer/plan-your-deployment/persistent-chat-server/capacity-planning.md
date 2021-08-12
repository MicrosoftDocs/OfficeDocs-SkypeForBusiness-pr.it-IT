---
title: Pianificazione della capacità per il server Chat persistente in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
description: 'Riepilogo: leggere questo argomento per informazioni sulla pianificazione della capacità per il server Chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 3b21ce2fdcb05101fb5a3fe1641e766003733fb7675331dbb12c273b1c44d7e6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54334837"
---
# <a name="capacity-planning-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Pianificazione della capacità per il server Chat persistente in Skype for Business Server 2015
 
**Riepilogo:** Leggere questo argomento per informazioni sulla pianificazione della capacità per il server Chat persistente in Skype for Business Server 2015.
  
Il server Chat persistente può eseguire chat multi-utente in tempo reale che possono persistere per il recupero e la ricerca futuri. A differenza della messaggistica istantanea di gruppo salvata nella cassetta postale di un utente se è configurata la cronologia delle conversazioni, una sessione del server Chat persistente rimane aperta più a lungo e il contenuto viene salvato su un server, insieme ai messaggi, ai file, agli URL e ad altri dati che fanno parte di una conversazione in corso.
  
La pianificazione della capacità è una parte importante della preparazione alla distribuzione del server Chat persistente. In questo argomento vengono fornite tabelle di pianificazione della capacità che è possibile utilizzare per determinare la configurazione migliore per la distribuzione. Viene inoltre descritto come gestire al meglio le distribuzioni del server Chat persistente che richiedono una maggiore capacità nelle ore di punta.
  
Prima di leggere questa sezione, è necessario avere familiarità con le topologie di Persistent Chat. Per ulteriori informazioni, vedere [Plan Persistent Chat Server topology](topology.md).

> [!NOTE] 
> La chat persistente è disponibile Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in Teams. Per ulteriori informazioni, vedere [Introduzione all'Microsoft Teams aggiornamento.](/microsoftteams/upgrade-start-here) Se è necessario utilizzare Persistent Chat, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità Teams o continuare a usare Skype for Business Server 2015. 
  
## <a name="persistent-chat-server-capacity-planning"></a>Pianificazione della capacità del server Chat persistente

Le tabelle seguenti consentono di pianificare la capacità per il server Chat persistente modellando il modo in cui le varie impostazioni del server Chat persistente influiscono sulla capacità.
  
- Pianificare la capacità per il numero di utenti
    
- Pianificare la capacità per l'accesso alle chat room
    
- Pianificare la capacità per l'accesso alle chat room tramite invito
    
- Pianificare la capacità per le prestazioni
    
### <a name="plan-capacity-for-number-of-users-for-persistent-chat-server"></a>Pianificare la capacità per il numero di utenti per il server Chat persistente

Utilizzare la tabella di esempio seguente per determinare il numero di utenti che sarà possibile supportare.
  
**Esempio di capacità massima del pool di server Chat persistente**

|||
|:-----|:-----|
|Istanze del servizio Chat persistente attive  <br/> |4   <br/> |
|Istanze del servizio Persistent Chat  <br/> |8 (può essere attivo solo un massimo di 4; 4 deve essere inattivo)  <br/> |
|Utenti attivi connessi  <br/> |80,000  <br/> |
|Totale utenti di cui è stato eseguito il provisioning  <br/> |150,000  <br/> |
|Numero di endpoint  <br/> |120,000  <br/> |
   
Nell'esempio precedente, il piano prevede il supporto del numero massimo di utenti consentito dal server Chat persistente: quattro server/istanze del servizio Chat persistente (possono avere altri quattro server passivi che eseguono il server Chat persistente per la disponibilità elevata e il ripristino di emergenza) e 20.000 utenti per server, per un totale di 80.000 utenti attivi.
  
### <a name="plan-capacity-for-chat-room-access"></a>Pianificare la capacità per l'accesso alle chat room

La tabella di esempio seguente consente di pianificare la gestione dell'accesso alle chat room in un pool di server Chat persistente.
  
**Esempio di gestione dell'accesso alle chat room**

||**Chat room di piccole dimensioni**|**Chat di medie dimensioni**|**Chat room di grandi dimensioni**|**Totale**|
|:-----|:-----|:-----|:-----|:-----|
|Dimensioni delle chat room (numero di utenti connessi)  <br/> |30 per sala  <br/> |150 per camera  <br/> |16.000 per camera  <br/> ||
|Chat  <br/> |32,000  <br/> |1,067  <br/> |10   <br/> |33,077  <br/> |
|% di sale auditorium  <br/> |1%  <br/> |1%  <br/> |50%  <br/> ||
|% di sale aperte  <br/> |3%  <br/> |3%  <br/> |50%  <br/> ||
|Sale aperte (nessuna appartenenza esplicita)  <br/> |960  <br/> |32  <br/> |5   <br/> |997  <br/> |
|Sale non aperte (sale regolari con appartenenza esplicita)  <br/> |31,040  <br/> |1.035  <br/> |5   <br/> |32,080  <br/> |
|Sale auditorium (voce relatori aggiuntivi)  <br/> |0  <br/> |32  <br/> |5   <br/> ||
|Sale gestite dall'appartenenza diretta  <br/> |50%  <br/> |10%  <br/> |0%  <br/> ||
|Chat gestite per gruppi di utenti  <br/> |50%  <br/> |90%  <br/> |100%  <br/> ||
|Gruppi di utenti nell'elenco di appartenenze di ogni chat room per le sale aperte (non specificato esplicitamente)  <br/> |0  <br/> |0  <br/> |0  <br/> ||
|Utenti nell'elenco di appartenenze di ogni chat room per le chat non aperte  <br/> |30  <br/> |150  <br/> |16,000  <br/> ||
|Gruppi di utenti nell'elenco di appartenenze di ogni chat room per le chat non aperte  <br/> |3   <br/> |5   <br/> |10   <br/> ||
|Utenti e gruppi di utenti nell'elenco dei manager di ogni chat room (per sale aperte e non aperte)  <br/> |6   <br/> |6   <br/> |6   <br/> ||
|Utenti e gruppi di utenti in ogni elenco di relatori di chat auditorium (per sale aperte e non aperte)  <br/> |6   <br/> |6   <br/> |6   <br/> ||
|Entità di appartenenza basata sull'utente in tutte le sale non aperte  <br/> |465,600  <br/> |15,520  <br/> |-  <br/> ||
|Entità di appartenenza basata su gruppi di utenti in tutte le sale non aperte  <br/> |46,560  <br/> |4656  <br/> |50  <br/> ||
|Entità basate su utenti e gruppi di utenti in tutte le chat room auditorium  <br/> |0  <br/> |192  <br/> |50  <br/> ||
|Entità manager basate su utenti e gruppi di utenti in tutti gli elenchi dei manager delle chat room  <br/> |192,000  <br/> |6,400  <br/> |60  <br/> ||
|Utenti attivi per chat  <br/> |30  <br/> |150  <br/> |16,000  <br/> ||
|Chat per utente  <br/> |12   <br/> |2  <br/> |2  <br/> |16   <br/> |
|Gruppi di utenti nell'elenco di appartenenze di ogni chat room  <br/> |10   <br/> |10   <br/> |15  <br/> ||
|Chat gestite per gruppi di utenti  <br/> |50%  <br/> |50%  <br/> |50%  <br/> ||
|Entità di appartenenza basata sui gruppi di utenti in tutte le chat  <br/> |155,200  <br/> |5173  <br/> |68  <br/> ||
|Entità di appartenenza basata sugli utenti in tutte le chat  <br/> |465,600  <br/> |77,600  <br/> |72,000  <br/> ||
|Utenti e gruppi di utenti in ogni elenco dei gestori delle chat, dei relatori delle chat e degli ambiti  <br/> |6   <br/> |6   <br/> |6   <br/> ||
|Utenti e gruppi di utenti in tutti gli elenchi di gestione, relatore e ambito di tutte le chat room  <br/> |192,000  <br/> |6400  <br/> |60  <br/> ||
|Voci di controllo di accesso  <br/> |704,160  <br/> |26,768  <br/> |160  <br/> |731,088  <br/> |
|Voci di controllo di accesso massime  <br/> ||||2,000,000  <br/> |
   
Nell'esempio precedente, quando si distribuiscono i server Chat persistente in base alle linee guida consigliate, possono gestire fino a 80.000 utenti attivi in un pool a quattro server con la conformità abilitata.
  
Questo esempio mostra le chat room classificate come piccole (30 utenti attivi in un determinato momento), medie (150 utenti attivi) e grandi (16.000 utenti attivi). Il numero supportato di chat room di una determinata dimensione nella tabella precedente viene calcolato in base al numero totale di:
  
- Utenti attivi nel sistema
    
- Utenti attivi nelle chat delle dimensioni specificate
    
- Chat delle dimensioni specificate cui partecipa ogni singole utente
    
Per ogni chat room, la tabella di pianificazione della capacità precedente specifica il numero di voci di controllo di accesso associate alla chat room, incluse le voci assegnate direttamente alla chat room. È possibile controllare l'accesso a singole chat tramite elenchi di controllo di accesso. È inoltre possibile controllare l'accesso a livello di categoria. In un ACL, una singola voce di controllo di accesso può essere un gruppo di utenti, ad esempio un gruppo di sicurezza, una lista di distribuzione o un singolo utente. È possibile definire voci di controllo di accesso per gestori, relatori e membri delle chat.
  
> [!IMPORTANT]
> Nella pianificazione della strategia per la gestione delle chat room, tenere presente che il numero totale di voci di controllo di accesso consentite è 2 milioni. Se le voci di controllo di accesso calcolate superano i 2 milioni, le prestazioni del server potrebbero peggiorare in modo significativo. Per evitare questo problema, quando possibile, assicurarsi che le voci di controllo di accesso siano gruppi di utenti anziché singoli utenti. 
  
### <a name="plan-capacity-for-managing-chat-room-access-by-invitation"></a>Pianificare la capacità per la gestione dell'accesso alle chat room tramite invito

È possibile utilizzare la seguente tabella di pianificazione della capacità per comprendere il numero di inviti creati e archiviati dal server Chat persistente nel database di Persistent Chat quando è configurato per l'invio di inviti. È possibile gestire gli inviti  nella categoria utilizzando la pagina Impostazioni categoria chat room nel Pannello di controllo di Skype for Business Server oppure utilizzando il cmdlet **Windows PowerShell, set-csPersistentChatCategory.** È possibile gestire gli inviti in una chat room (in  linea con quanto la categoria consente) utilizzando la pagina Gestione chat avviata dal client Skype for Business oppure utilizzando un cmdlet di Windows PowerShell, **set-csPersistentChatRoom.**
  
I dati di esempio nella tabella seguente presuppongono che nella pagina **Impostazioni**  chat room per il 50% di tutte le chat room l'opzione Inviti sia impostata su **Sì.**
  
> [!IMPORTANT]
> Se il valore calcolato per il numero di inviti generati dal server supera 1 milione, le prestazioni del server potrebbero peggiorare in modo significativo. Per evitare questo problema, assicurarsi di ridurre al minimo il numero di chat configurate per inviare inviti o limitare il numero di utenti che possono partecipare alle chat room configurate per l'invio di inviti. 
  
**Esempio di accesso alle chat room tramite invito**

||**Chat room di piccole dimensioni**|**Chat di medie dimensioni**|**Chat room di grandi dimensioni**|**Totale**|
|:-----|:-----|:-----|:-----|:-----|
|Utenti che possono accedere alla chat room  <br/> |30 per sala  <br/> |150 per camera  <br/> |16.000 per camera  <br/> ||
|Percentuale di sale con inviti  <br/> |50%  <br/> |50%  <br/> |50%  <br/> ||
|Chat configurate per l'invio di inviti  <br/> |16,000  <br/> |533  <br/> |5   <br/> ||
|Utenti che possono accedere alla chat  <br/> |60  <br/> |225  <br/> |16,000  <br/> ||
|Inviti generati dal server Chat persistente  <br/> |960,000  <br/> |120,000  <br/> |80,000  <br/> |1,160,000  <br/> |
|Numero massimo consentito di inviti  <br/> ||||2,000,000  <br/> |
|Modello 1 - Iniziare con il numero previsto di messaggi per sala al giorno  <br/> |||||
|Frequenza chat per sala (al giorno)  <br/> |50  <br/> |500  <br/> |100  <br/> |650  <br/> |
|Frequenza chat (al secondo) in tutte le chat room  <br/> |55.56  <br/> |18.52  <br/> |0.03  <br/> |74  <br/> |
|Modello 2 - Iniziare con il numero di messaggi pubblicati per utente al giorno  <br/> |||||
|Frequenza chat per utente al giorno  <br/> |15  <br/> |5   <br/> |0.1  <br/> |20  <br/> |
|Frequenza chat per sala (al giorno)  <br/> |38  <br/> |375  <br/> |800  <br/> |1,213  <br/> |
|Frequenza chat (al secondo) in tutte le chat room  <br/> |41.67  <br/> |13.89  <br/> |0.28  <br/> |56  <br/> |
   
### <a name="plan-capacity-for-persistent-chat-server-performance"></a>Pianificare la capacità per le prestazioni del server Chat persistente

Nella tabella seguente viene descritto il modello utente per il server Chat persistente. Fornisce la base per i requisiti di pianificazione della capacità e rappresenta un'organizzazione tipica con 80.000 utenti simultanei su quattro server.
  
**Modello utente per le prestazioni del server Chat persistente**

|||
|:-----|:-----|
|Numero di utenti attivi connessi  <br/> |80,000  <br/> |
|Numero di istanze del servizio Server Chat persistente  <br/> |4   <br/> |
|Numero di utenti di chat di piccole dimensioni  <br/> |30 utenti  <br/> |
|Numero di utenti di chat di medie dimensioni  <br/> |150 utenti  <br/> |
|Numero di utenti di chat di grandi dimensioni  <br/> |16.000 utenti  <br/> |
|Numero totale di chat  <br/> |33,077  <br/> |
|Numero di chat di piccole dimensioni  <br/> |32,000  <br/> |
|Numero di chat di medie dimensioni  <br/> |1,067  <br/> |
|Numero di chat di grandi dimensioni  <br/> |10   <br/> |
|Numero totale di chat per utente  <br/> |16   <br/> |
|Numero di chat di piccole dimensioni per utente  <br/> |12   <br/> |
|Numero di chat di medie dimensioni per utente  <br/> |2  <br/> |
|Numero di chat di grandi dimensioni per utente  <br/> |2  <br/> |
|Numero di chat room unite per utente  <br/> |24  <br/> |
|Frequenza di partecipazione di punta  <br/> |10/secondo  <br/> |
|Frequenza di chat totale  <br/> |24/secondo  <br/> |
|Frequenza di chat per chat di piccole dimensioni  <br/> |22,22/secondo  <br/> |
|Frequenza di chat per chat di medie dimensioni  <br/> |1,67/secondo  <br/> |
|Frequenza di chat per chat di grandi dimensioni  <br/> |~0,15/secondo  <br/> |
|Percentuale di chat configurate per l'invio di inviti  <br/> |50%  <br/> |
|Percentuale di appartenenza diretta  <br/> |50%  <br/> |
|Percentuale di appartenenza a gruppi  <br/> |50%  <br/> |
|Numero medio di affiliazioni predecessore in Servizi di dominio Active Directory  <br/> |100 - 200  <br/> |
|Numero di contatti sottoscritti per utente  <br/> |80  <br/> |
|Numero medio di endpoint per utente  <br/> |1.5  <br/> |
|Numero medio di chat visibili per endpoint  <br/> |1.5  <br/> |
|Numero medio di chat visibili per utente  <br/> |2,25 (50% per 1 camera e 50% per 2 sale); Fino a 6 sale aperte, una per monitor  <br/> |
|Numero di partecipanti sottoposti a polling per intervallo  <br/> |25 per chat visibile  <br/> |
|Durata dell'intervallo di polling  <br/> |5 minuti  <br/> |
|Numero di partecipanti sottoposti a polling al secondo  <br/> |15.000  <br/> |
|Numero di modifiche delle informazioni sulla presenza all'ora per utente  <br/> |6   <br/> |
|Numero di modifiche delle informazioni sulla presenza al secondo  <br/> |133.33  <br/> |
   

