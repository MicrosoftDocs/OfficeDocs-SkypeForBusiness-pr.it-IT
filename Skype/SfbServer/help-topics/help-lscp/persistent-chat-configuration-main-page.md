---
title: Pagina principale Configurazione di Chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatConfigMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e75d352-12cf-4548-9301-5d4c0e1c8f46
description: La distribuzione del server di chat persistente può ospitare molte chat room persistenti simultanee. Le chat room possono essere organizzate in un set di categorie nel server. Ogni chat room appartiene a una sola categoria ed eredita alcune impostazioni da tale categoria. In questo modo viene creata una struttura utile per identificare le conversazioni in base alle esigenze aziendali e per facilitare l'amministrazione delegata e la gestione semplificata.
ms.openlocfilehash: de5ce1825a31f37dadbe36e7bcedaa5ec52542dc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188243"
---
# <a name="persistent-chat-configuration-main-page"></a>Pagina principale Configurazione di Chat persistente
 
La distribuzione del server di chat persistente può ospitare molte chat room persistenti simultanee. Le chat room possono essere organizzate in un set di categorie nel server. Ogni chat room appartiene a una sola categoria ed eredita alcune impostazioni da tale categoria. In questo modo viene creata una struttura utile per identificare le conversazioni in base alle esigenze aziendali e per facilitare l'amministrazione delegata e la gestione semplificata.
  
> [!NOTE]
> Anche se molte delle caratteristiche di gestione delle chat room sono disponibili nei computer che eseguono la chat persistente per l'utente, gli amministratori della chat persistente (nel ruolo **CsPersistentChatAdministrator** ) devono usare il pannello di controllo o i cmdlet di Management Shell per creare o gestire categorie.
  
Gli amministratori della chat persistente usano il pannello di controllo di Skype for Business Server o i cmdlet di Windows PowerShell per creare e gestire categorie e per progettare l'accesso per le chat room per gli utenti dell'organizzazione.
  
I responsabili delle chat room permanenti, che hanno la possibilità di gestire una o più chat room, possono usare il client per avviare un'applicazione Web di gestione delle room per creare e gestire le sale (o i clienti possono creare soluzioni e flussi di lavoro personalizzati da richiamare). 
  
I responsabili delle chat room possono apportare modifiche a tutte le proprietà delle chat room, con l'eccezione della modifica della categoria. Non è possibile impedire loro di eseguire le azioni seguenti:
  
- Disabilitare una chat room
    
- Modificare il nome di una chat room
    
- Modificare la descrizione di una chat room
    
- Modificare il tipo di chat room (auditorium o normale)
    
- Modificare la privacy di una chat room (aperta, chiusa o segreta)
    
- Aggiungere o rimuovere membri
    
- Aggiungere o rimuovere responsabili di chat room
    
- Aggiungere o rimuovere componenti aggiuntivi
    
- Modifica delle impostazioni, ad esempio gli inviti (in base a quanto consentito dalla categoria)
    
## <a name="tasks-that-you-can-perform"></a>Attività che è possibile eseguire

Nella pagina di **configurazione della chat persistente** è possibile eseguire le attività seguenti: configurare le opzioni del server di chat persistenti a livello globale o per un pool specifico
  
## <a name="to-configure-persistent-chat-options-globally"></a>Per configurare le opzioni di chat persistenti a livello globale

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
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>Per configurare le opzioni di chat persistenti per un pool di server di chat persistente specifico

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
    
## <a name="see-also"></a>Vedere anche

Per informazioni dettagliate sulle funzionalità e le funzionalità del server di chat persistente, vedere [pianificare il server di chat persistente in Skype for Business server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [distribuire il server di chat persistente in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)e [gestire il server di chat persistente in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

