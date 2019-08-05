---
title: Configurare le opzioni del server Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: 'Riepilogo: informazioni su come configurare le opzioni del server di chat persistenti a livello globale, del sito o del pool in Skype for Business Server 2015.'
ms.openlocfilehash: 3140689190900bee1633210a455c7af475bb8fa0
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "36195951"
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a>Configurare le opzioni del server Chat persistente
 
**Riepilogo:** Informazioni su come configurare le opzioni del server di chat persistenti a livello globale, del sito o del pool in Skype for Business Server 2015.
  
È possibile specificare diverse opzioni per il server di chat persistente che può essere applicato a livello globale, a tutti i pool all'interno di un sito o a uno specifico pool all'interno di un sito. Le opzioni del server di chat persistenti includono le seguenti: 
  
- Cronologia chat predefinita. Numero di messaggi di chat disponibili per ogni chat room al momento della prima richiesta. Il valore predefinito globale è 30 messaggi di chat. 
    
- Dimensione massima del file. Le dimensioni massime di un file che è possibile caricare o scaricare da una chat room. Il valore predefinito globale è 20MB.
    
- Limite di aggiornamento dei partecipanti. Numero massimo di partecipanti in una determinata chat room per cui la chat persistente invierà gli aggiornamenti del roster. Il valore predefinito globale è 75.
    
- URL di gestione delle chat room. URL usato per la gestione delle chat room personalizzate. L'impostazione consente l'uso di una soluzione di gestione delle sale personalizzata. 
   
> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario usare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team o continuare a usare Skype for Business Server 2015.
 
## <a name="configure-persistent-chat-server-global-options"></a>Configurare le opzioni globali del server di chat persistente

Per configurare le opzioni globali del server di chat persistente:
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a un qualsiasi computer nella distribuzione interna.
    
2. Nel menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore.
    
3. Sulla barra di spostamento sinistra fare clic su **Chat persistente** e quindi su **Configurazione di Chat persistente**.
    
4. Nella pagina di **configurazione della chat persistente** fare clic su **nuovo** e quindi su **configurazione sito**.
    
    > [!IMPORTANT]
    > Scegliere questa opzione se si vuole che la configurazione venga applicata a tutti i pool di server di chat persistenti distribuiti nel sito. Fare clic su **Configurazione pool** se si vuole che la configurazione venga applicata a un pool di server di chat persistente specifico.
  
5. In **Seleziona un sito**selezionare il sito da configurare per la configurazione del sito del server Chat persistente.
    
6. In **Nuova configurazione di Chat persistente** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per le nuove impostazioni di configurazione. Per impostazione predefinita, il nome del sito esiste già.
    
   - In **Cronologia chat predefinita** definire il numero di messaggi chat che verranno elaborati per ogni chat room alla prima richiesta. Per impostazione predefinita, il numero è 30. Si tratta dell'impostazione globale predefinita e gli amministratori possono disabilitare la cronologia chat per categoria.
    
     > [!IMPORTANT]
     > Il server di chat persistente memorizza nella cache questi messaggi in memoria, quindi se si aumenta questo numero, verrà memorizzato nella cache altri messaggi. È sempre possibile accedere al contenuto cronologico tramite ricerca. Il numero predefinito determina semplicemente il numero massimo di messaggi visualizzati inizialmente alla connessione a una chat room. 
  
   - In **Dimensioni massime file (KB)** selezionare le dimensioni file massime di ogni cronologia chat. Per impostazione predefinita, il numero è 20 MB (20.000 KB). Si tratta delle dimensioni massime per un file caricabile in qualsiasi chat room nel sistema (per cui i caricamenti sono abilitati attraverso la relativa impostazione **Categoria**).
    
   - In **Limite di aggiornamento partecipanti** selezionare il limite per gli aggiornamenti dei partecipanti. Il server di chat persistente invia le informazioni del roster (che sono connesse a una chat room) a tutti i partecipanti finché il numero di utenti connessi non raggiunge questo numero. Per impostazione predefinita, il numero è 75. Questo limite indica il numero massimo di partecipanti in una determinata sala oltre la quale il server di chat persistente smette di inviare aggiornamenti di Roster ai client connessi su chi è presente nella sala.
    
   - (Facoltativo) Nell' **URL gestione sala**selezionare l'URL di gestione della sala. Si tratta dell'URL di una gestione chat room personalizzata basata sul Web. Se non è necessario personalizzare la gestione delle chat room e si usa semplicemente l'impostazione predefinita, uscire da questa opzione vuota. Dopo essere stato impostato, l'URL viene applicato come URL di gestione chat room interna ed esterna.
    
     Se si vuole personalizzare l'esperienza di creazione di una sala e includere un flusso di lavoro aziendale specifico, è possibile creare una soluzione di gestione delle sale personalizzata usando il Software Development Kit (SDK) di Persistent Chat Server, ospitarlo da qualche parte e inserire l'URL qui. Questo URL viene inviato al client in modo che quando un utente tenta di visualizzare o creare una chat room, viene indirizzato alla soluzione di gestione personalizzata.
    
7. Fare clic su **Commit**.
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a>Configurare le opzioni per un pool di server di chat persistente specifico

Per configurare le opzioni per un pool di server di chat persistente specifico.
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a un qualsiasi computer nella distribuzione interna.
    
2. Nel menu **Start** selezionare il pannello di controllo di Skype for Business Server oppure aprire una finestra del browser e quindi immettere l'URL dell'amministratore.
    
3. Sulla barra di spostamento sinistra fare clic su **Chat persistente** e quindi su **Configurazione di Chat persistente**.
    
4. Nella pagina **Configurazione di Chat persistente** fare clic su **Nuovo** e quindi su **Configurazione pool**.
    
5. In **Seleziona un servizio**selezionare il servizio associato al pool di server di chat persistente da configurare.
    
6. In **Nuova configurazione di Chat persistente** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per le nuove impostazioni di configurazione. Per impostazione predefinita, il nome del pool esiste già.
    
   - In **Cronologia chat predefinita** definire il numero di messaggi chat che verranno elaborati per ogni chat room alla prima richiesta. Per impostazione predefinita, il numero è 30. Si tratta dell'impostazione globale predefinita e gli amministratori possono disabilitare la cronologia chat per categoria.
    
     > [!IMPORTANT]
     > Il server di chat persistente memorizza nella cache questi messaggi in memoria, quindi se si aumenta questo numero, verrà memorizzato nella cache altri messaggi. È sempre possibile accedere al contenuto cronologico tramite ricerca. Il numero predefinito determina semplicemente il numero massimo di messaggi visualizzati inizialmente alla connessione a una chat room. 
  
   - In **Dimensioni massime file (KB)** selezionare le dimensioni file massime di ogni cronologia chat. Per impostazione predefinita, il numero è 20 MB (20.000 KB). Si tratta delle dimensioni massime per un file caricabile in qualsiasi chat room nel sistema (per cui i caricamenti sono abilitati attraverso la relativa impostazione **Categoria**).
    
   - In **Limite di aggiornamento partecipanti** selezionare il limite per gli aggiornamenti dei partecipanti. Il server di chat persistente invia le informazioni del roster (che sono connesse a una chat room) a tutti i partecipanti finché il numero di utenti connessi non raggiunge questo numero. Per impostazione predefinita, il numero è 75. Questo limite indica il numero massimo di partecipanti in una determinata sala oltre la quale il server di chat persistente smette di inviare aggiornamenti di Roster ai client connessi su chi è presente nella sala.
    
   - In **URL gestione chat** selezionare l'URL di gestione della chat room. Si tratta dell'URL di una distribuzione di gestione chat room basata sul Web. Se non è necessario personalizzare la gestione delle chat room e si usa semplicemente l'impostazione predefinita, uscire da questa opzione vuota.
    
     Se si vuole personalizzare l'esperienza di creazione di una sala e includere un flusso di lavoro aziendale specifico, è possibile creare una soluzione di gestione delle sale personalizzata usando il Software Development Kit (SDK) di Persistent Chat Server, ospitarlo da qualche parte e inserire l'URL qui. Questo URL viene inviato al client in modo che quando un utente tenta di visualizzare o creare una chat room, viene indirizzato alla soluzione di gestione personalizzata.
    
7. Fare clic su **Commit**.
    

