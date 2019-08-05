---
title: Pianificazione della capacità del server Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
description: 'Riepilogo: leggere questo argomento per informazioni sulla pianificazione della capacità per il server di chat persistente in Skype for Business Server 2015.'
ms.openlocfilehash: 7aa76aecf183fc0872adf6f6040132310d54a989
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "36195991"
---
# <a name="capacity-planning-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Pianificazione della capacità del server Chat persistente
 
**Riepilogo:** Leggere questo argomento per informazioni sulla pianificazione della capacità per il server di chat persistente in Skype for Business Server 2015.
  
Il server di chat persistente può eseguire chat multiutente e in tempo reale che possono persistere per il recupero e la ricerca futuri. A differenza della messaggistica istantanea di gruppo che viene salvata nella cassetta postale di un utente se è configurata la cronologia delle conversazioni, una sessione del server di chat persistente rimane aperta più a lungo e il contenuto viene salvato in un server, insieme ai messaggi, ai file, agli URL e ad altri dati che fanno parte di un conversazione in corso.
  
La pianificazione della capacità è una parte importante della preparazione alla distribuzione del server di chat persistente. Questo argomento fornisce le tabelle di pianificazione della capacità che è possibile usare per determinare la configurazione migliore per la distribuzione. Descrive anche come gestire al meglio le distribuzioni del server della chat persistente che richiedono maggiore capacità nelle ore di punta.
  
Prima di leggere questa sezione, dovresti avere familiarità con le topologie della chat persistente. Per altre informazioni, vedere [pianificare](topology.md)la topologia del server di chat persistente.

> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015. 
  
## <a name="persistent-chat-server-capacity-planning"></a>Pianificazione della capacità del server di chat persistente

Le tabelle seguenti possono essere utili per la pianificazione della capacità per il server della chat persistente modellando la capacità delle varie impostazioni del server di chat persistente.
  
- Pianificare la capacità per il numero di utenti
    
- Pianificare la capacità per l'accesso alle chat room
    
- Pianificare la capacità per l'accesso alle chat room tramite invito
    
- Pianificare la capacità di prestazioni
    
### <a name="plan-capacity-for-number-of-users-for-persistent-chat-server"></a>Pianificare la capacità per il numero di utenti per il server di chat persistente

Usare la tabella di esempio seguente per determinare il numero di utenti che sarà in grado di supportare.
  
**Esempio di capacità massima del pool di server di chat persistente**

|||
|:-----|:-----|
|Istanze del servizio chat persistenti attive  <br/> |4  <br/> |
|Istanze del servizio chat persistente  <br/> |8 (può essere attivo solo un massimo di 4; 4 deve essere inattivo)  <br/> |
|Utenti attivi connessi  <br/> |80.000  <br/> |
|Totale utenti con provisioning  <br/> |150.000  <br/> |
|Numero di endpoint  <br/> |120.000  <br/> |
   
Nell'esempio precedente il piano consiste nel supportare il numero massimo di utenti che il server di chat persistente consente: quattro server/istanze del servizio di chat persistente (può avere quattro server più passivi in cui è in uso il server di chat persistente per l'elevata disponibilità e Disaster Recovery) e 20.000 utenti per server, per un totale di 80.000 utenti attivi.
  
### <a name="plan-capacity-for-chat-room-access"></a>Pianificare la capacità per l'accesso alle chat room

La tabella di esempio seguente può aiutare a pianificare la gestione dell'accesso alle chat room in un pool di server di chat persistente.
  
**Esempio di accesso alla chat room**

||**Piccole chat room**|**Chat room di medie dimensioni**|**Chat room di grandi dimensioni**|**Totale**|
|:-----|:-----|:-----|:-----|:-----|
|Dimensioni delle chat room (numero di utenti connessi)  <br/> |30 per camera  <br/> |150 per camera  <br/> |16.000 per camera  <br/> ||
|Chat room  <br/> |32.000  <br/> |1.067  <br/> |10  <br/> |33.077  <br/> |
|% delle sale che sono Auditorium  <br/> |1  <br/> |1  <br/> |50%  <br/> ||
|% delle camere aperte  <br/> |3  <br/> |3  <br/> |50%  <br/> ||
|Aprire le sale (nessuna appartenenza esplicita)  <br/> |960  <br/> |32  <br/> |5  <br/> |997  <br/> |
|Camere non aperte (camere normali con appartenenza esplicita)  <br/> |31.040  <br/> |1,035  <br/> |5  <br/> |32.080  <br/> |
|Sale Auditorium (voce relatori aggiunti)  <br/> |0  <br/> |32  <br/> |5  <br/> ||
|Sale gestite da un abbonamento diretto  <br/> |50%  <br/> |10  <br/> |0  <br/> ||
|Sale gestite da gruppi di utenti  <br/> |50%  <br/> |90%  <br/> |100%  <br/> ||
|Gruppi di utenti nell'elenco di appartenenza di ogni chat room per le camere aperte (non specificato in modo esplicito)  <br/> |0  <br/> |0  <br/> |0  <br/> ||
|Utenti nell'elenco di appartenenza di ogni chat room per le camere non aperte  <br/> |30  <br/> |150  <br/> |16.000  <br/> ||
|Gruppi di utenti nell'elenco di appartenenza di ogni chat room per le camere non aperte  <br/> |3  <br/> |5  <br/> |10  <br/> ||
|Utenti e gruppi utenti nell'elenco Manager di ogni chat room (per le sale aperte e non aperte)  <br/> |6  <br/> |6  <br/> |6  <br/> ||
|Utenti e gruppi utenti nell'elenco relatori di ogni chat room dell'Auditorium (per le sale aperte e non aperte)  <br/> |6  <br/> |6  <br/> |6  <br/> ||
|Entità di appartenenza basate sull'utente in tutte le camere non aperte  <br/> |465.600  <br/> |15.520  <br/> |-  <br/> ||
|Entità di appartenenza basate su gruppi di utenti in tutte le camere non aperte  <br/> |46.560  <br/> |4656  <br/> |50  <br/> ||
|Utenti e gruppi utente basati su entità in tutte le chat room di Auditorium  <br/> |0  <br/> |192  <br/> |50  <br/> ||
|Gli utenti e le entità di gestione basate su gruppi utente in tutti gli elenchi di Manager di chat room  <br/> |192.000  <br/> |6.400  <br/> |60  <br/> ||
|Utenti attivi per chat room  <br/> |30  <br/> |150  <br/> |16.000  <br/> ||
|Chat room per utente  <br/> |12  <br/> |2  <br/> |2  <br/> |16  <br/> |
|Gruppi di utenti nell'elenco di appartenenza di ogni chat room  <br/> |10  <br/> |10  <br/> |15  <br/> ||
|Sale gestite da gruppi di utenti  <br/> |50%  <br/> |50%  <br/> |50%  <br/> ||
|Entità di appartenenza basate su gruppi di utenti in tutte le chat room  <br/> |155.200  <br/> |5173  <br/> |68  <br/> ||
|Entità di appartenenza basate sull'utente in tutte le chat room  <br/> |465.600  <br/> |77.600  <br/> |72.000  <br/> ||
|Utenti e gruppi utenti negli elenchi Manager, relatore e ambito di ogni chat room  <br/> |6  <br/> |6  <br/> |6  <br/> ||
|Utenti e gruppi utenti in tutte le chat room Manager, relatore e elenchi di ambiti  <br/> |192.000  <br/> |6400  <br/> |60  <br/> ||
|Voci di controllo di Access  <br/> |704.160  <br/> |26.768  <br/> |160  <br/> |731.088  <br/> |
|Voci di controllo di accesso massimo  <br/> ||||2 milioni  <br/> |
   
Nell'esempio precedente, quando si distribuiscono i server di chat persistenti in base alle linee guida consigliate, è possibile gestire fino a 80.000 utenti attivi in un pool di quattro server con conformità abilitata.
  
Questo esempio mostra le chat room categorizzate come piccole (30 utenti attivi in qualsiasi momento), medie (utenti attivi di 150) e grandi (16.000 utenti attivi). Il numero supportato di chat room di una determinata dimensione nella tabella precedente viene calcolato in base al numero totale di:
  
- Utenti attivi nel sistema
    
- Utenti attivi nelle chat room delle dimensioni specificate
    
- Chat room con le dimensioni specificate a cui è associato un singolo utente
    
Per ogni chat room, la tabella di pianificazione della capacità precedente specifica il numero di voci di controllo di accesso associate alla chat room, incluse le voci assegnate direttamente alla chat room. È possibile controllare l'accesso alle singole chat room usando gli elenchi di controllo di accesso (ACL). È anche possibile controllare l'accesso a livello di categoria. In un ACL una singola voce di controllo di accesso può essere un gruppo di utenti, ad esempio un gruppo di sicurezza, una lista di distribuzione o un singolo utente. Puoi definire le voci di controllo di accesso per i responsabili delle chat room, i relatori e i membri.
  
> [!IMPORTANT]
> Nella pianificazione della strategia per la gestione delle chat room, tieni presente che il numero totale di voci di controllo di accesso consentite è 2 milioni. Se le voci di controllo di accesso calcolate superano 2 milioni, le prestazioni del server potrebbero peggiorare in modo significativo. Per evitare questo problema, se possibile, verificare che le voci di controllo di accesso siano gruppi di utenti anziché singoli. 
  
### <a name="plan-capacity-for-managing-chat-room-access-by-invitation"></a>Pianificare la capacità di gestione dell'accesso alle chat room tramite invito

È possibile usare la tabella di pianificazione della capacità seguente per comprendere il numero di inviti che il server di chat persistente crea e archivia nel database della chat persistente quando è configurato per l'invio di inviti. Puoi gestire gli inviti per la categoria usando la pagina **delle impostazioni della categoria chat room** nel pannello di controllo di Skype for Business Server oppure usando il cmdlet di Windows PowerShell, **set-csPersistentChatCategory**. Puoi gestire gli inviti in una chat room (in linea con ciò che la categoria consente) usando la pagina **gestione sala** avviata dal client Skype for business o usando un cmdlet di Windows PowerShell, **set-csPersistentChatRoom**.
  
I dati di esempio nella tabella seguente presuppongono che, nella pagina **delle impostazioni della chat room** per 50% di tutte le **** chat room, l'opzione inviti sia impostata su **Sì**.
  
> [!IMPORTANT]
> Se il valore calcolato per il numero di inviti generati dal server supera 1 milione, le prestazioni del server potrebbero peggiorare in modo significativo. Per evitare questo problema, assicurati di ridurre al minimo il numero di chat room configurate per l'invio di inviti o per limitare il numero di utenti che possono partecipare alle chat room configurate per l'invio di inviti. 
  
**Accesso alla chat room tramite l'esempio di invito**

||**Piccole chat room**|**Chat room di medie dimensioni**|**Chat room di grandi dimensioni**|**Totale**|
|:-----|:-----|:-----|:-----|:-----|
|Utenti che possono accedere alla chat room  <br/> |30 per camera  <br/> |150 per camera  <br/> |16.000 per camera  <br/> ||
|Percentuale di camere con inviti  <br/> |50%  <br/> |50%  <br/> |50%  <br/> ||
|Chat room configurate per l'invio di inviti  <br/> |16.000  <br/> |533  <br/> |5  <br/> ||
|Utenti che possono accedere alla chat room  <br/> |60  <br/> |225  <br/> |16.000  <br/> ||
|Inviti generati dal server di chat persistente  <br/> |960.000  <br/> |120.000  <br/> |80.000  <br/> |1.160.000  <br/> |
|Numero massimo di inviti consentiti  <br/> ||||2 milioni  <br/> |
|Modello 1-iniziare con il numero di messaggi previsto per ogni camera al giorno  <br/> |||||
|Tasso di chat per camera (per giorno)  <br/> |50  <br/> |500  <br/> |100  <br/> |650  <br/> |
|Velocità di chat (al secondo) in tutte le sale  <br/> |55,56  <br/> |18,52  <br/> |0,03  <br/> |74  <br/> |
|Modello 2-inizio con il numero di messaggi pubblicati per utente per giorno  <br/> |||||
|Tasso di chat per utente per giorno  <br/> |15  <br/> |5  <br/> |0,1  <br/> |20  <br/> |
|Tasso di chat per camera (per giorno)  <br/> |38  <br/> |375  <br/> |800  <br/> |1.213  <br/> |
|Velocità di chat (al secondo) in tutte le sale  <br/> |41,67  <br/> |13,89  <br/> |0,28  <br/> |56  <br/> |
   
### <a name="plan-capacity-for-persistent-chat-server-performance"></a>Pianificare la capacità delle prestazioni del server della chat persistente

La tabella seguente descrive il modello di utente per il server di chat persistente. Fornisce la base per i requisiti di pianificazione della capacità e rappresenta un'organizzazione tipica con utenti simultanei di 80.000 su quattro server.
  
**Modello utente delle prestazioni del server di chat persistente**

|||
|:-----|:-----|
|Numero di utenti attivi connessi  <br/> |80.000  <br/> |
|Numero di istanze del servizio server Chat persistente  <br/> |4  <br/> |
|Dimensioni delle piccole chat room  <br/> |30 utenti  <br/> |
|Dimensioni delle chat room medie  <br/> |utenti di 150  <br/> |
|Dimensioni delle chat room di grandi dimensioni  <br/> |utenti di 16.000  <br/> |
|Numero totale di chat room  <br/> |33.077  <br/> |
|Numero di chat room di piccole dimensioni  <br/> |32.000  <br/> |
|Numero di chat room di medie dimensioni  <br/> |1.067  <br/> |
|Numero di chat room di grandi dimensioni  <br/> |10  <br/> |
|Numero totale di chat room per utente  <br/> |16  <br/> |
|Numero di piccole chat room per utente  <br/> |12  <br/> |
|Numero di chat room medie per utente  <br/> |2  <br/> |
|Numero di chat room di grandi dimensioni per utente  <br/> |2  <br/> |
|Numero di sale Unite per utente  <br/> |24  <br/> |
|Tasso di partecipazione di picco  <br/> |10/secondo  <br/> |
|Tasso di chat totale  <br/> |24/secondo  <br/> |
|Tariffa chat per piccole chat room  <br/> |22.22/second  <br/> |
|Tasso di chat per le chat room di medie dimensioni  <br/> |1.67/Second  <br/> |
|Tasso di chat per le chat room di grandi dimensioni  <br/> |~ 0.15/secondo  <br/> |
|Percentuale di chat room configurate per gli inviti  <br/> |50%  <br/> |
|Percentuale di appartenenze dirette  <br/> |50%  <br/> |
|Percentuale di appartenenze ai gruppi  <br/> |50%  <br/> |
|Numero medio di affiliazioni predecessore in servizi di dominio Active Directory  <br/> |100-200  <br/> |
|Numero di contatti sottoscritti per utente  <br/> |80  <br/> |
|Numero medio di endpoint per utente  <br/> |1,5  <br/> |
|Numero medio di chat room visibili per endpoint  <br/> |1,5  <br/> |
|Numero medio di chat room visibili per utente  <br/> |2,25 (50% per 1 sala e 50% per 2 sale); Fino a 6 camere aperte, una per ogni monitor  <br/> |
|Numero di partecipanti interrogati per intervallo  <br/> |25 per la chat room visibile  <br/> |
|Lunghezza dell'intervallo di polling  <br/> |5 minuti  <br/> |
|Numero di partecipanti a polling al secondo  <br/> |15.000  <br/> |
|Numero di modifiche alla presenza per ora per utente  <br/> |6  <br/> |
|Numero di modifiche alla presenza al secondo  <br/> |133,33  <br/> |
   

