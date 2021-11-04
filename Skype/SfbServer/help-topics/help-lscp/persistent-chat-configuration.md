---
title: Configurazione Persistent Chat
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatConfig
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3f2891e6-bad3-4a23-a345-b7de4cae3bd9
description: La distribuzione del server Chat persistente può ospitare molte chat room persistenti simultanee. Le chat room possono essere organizzate in una serie di categorie sul server. Ogni chat room appartiene a una categoria, da cui eredita alcune impostazioni. In questo modo viene creata una struttura che consente di identificare le conversazioni in base alle esigenze aziendali e di facilitare l'amministrazione delegata e la gestione semplificata.
ms.openlocfilehash: e3b425e56b8d32c7066294c3794cad9979d832ff
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60748202"
---
# <a name="persistent-chat-configuration"></a>Configurazione di Chat persistente
 
La distribuzione del server Chat persistente può ospitare molte chat room persistenti simultanee. Le chat room possono essere organizzate in una serie di categorie sul server. Ogni chat room appartiene a una categoria, da cui eredita alcune impostazioni. In questo modo viene creata una struttura che consente di identificare le conversazioni in base alle esigenze aziendali e di facilitare l'amministrazione delegata e la gestione semplificata.
  
> [!NOTE]
> Sebbene molte delle funzionalità di gestione delle chat room siano disponibili nei computer che eseguono Persistent Chat per l'utente, gli amministratori di Persistent Chat (nel ruolo **cspersistentchatadministrator)** devono utilizzare il Pannello di controllo o i cmdlet della shell di gestione per creare o gestire le categorie.
  
Gli amministratori di Chat persistente utilizzano Skype for Business Server pannello di controllo o cmdlet Windows PowerShell per creare e gestire categorie e per progettare l'accesso alle chat room per gli utenti dell'organizzazione.
  
I responsabili delle chat persistenti, che hanno la possibilità di gestire una o più chat room, possono utilizzare il client per avviare un'applicazione Web di gestione delle chat room per creare e gestire le chat (oppure i clienti possono creare soluzioni e flussi di lavoro personalizzati da richiamare). Chat persistente
  
Gli amministratori di Persistent Chat possono inoltre utilizzare il Pannello di controllo o Windows PowerShell cmdlet per creare e gestire le chat room.
  
I responsabili delle chat room possono apportare modifiche a tutte le proprietà delle chat room, ad eccezione della categoria della chat. Non è invece possibile impedire loro di eseguire le azioni seguenti:
  
- Disabilitazione di una chat room
    
- Modifica del nome di una chat room
    
- Modifica della descrizione di una chat room
    
- Modifica del tipo di chat room (Auditorium o Normale)
    
- Modifica della privacy di una chat (aperta, chiusa o segreta)
    
- Aggiunta o rimozione di membri
    
- Aggiunta o rimozione di responsabili della chat room
    
- Aggiunta o rimozione di componenti aggiuntivi
    
- Modifica delle impostazioni, ad esempio gli inviti (in base a quanto consentito dalla categoria)
    
## <a name="tasks-that-you-can-perform"></a>Attività eseguibili

Nella pagina Configurazione chat **persistente** è possibile eseguire le attività seguenti: configurare le opzioni del server Chat persistente a livello globale o per un pool specifico.
  
## <a name="to-configure-persistent-chat-options-globally"></a>Per configurare le opzioni di Persistent Chat a livello globale

1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** seleziona il pannello Skype for Business Server o apri una finestra del browser e quindi immetti l'URL di amministratore.
    
3. Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Configurazione Persistent Chat**.
    
4. Nella pagina **Configurazione Persistent Chat** fare clic su Nuovo **e** quindi su **Configurazione sito.**
    
    > [!IMPORTANT]
    > Scegliere questa opzione se si desidera applicare la configurazione a tutti i pool di server Chat persistente distribuiti nel sito. Fare **clic su Configurazione** pool se si desidera applicare la configurazione a uno specifico pool di server Chat persistente.
  
5. In **Selezionare un sito** selezionare il sito da configurare per la configurazione del sito del server Chat persistente.
    
6. In **Nuova configurazione Persistent Chat** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per le nuove impostazioni di configurazione. Per impostazione predefinita, il nome del sito esiste già.
    
   - In **Cronologia chat predefinita** definire il numero di messaggi chat che verranno elaborati per ogni chat alla prima richiesta. Per impostazione predefinita, questo numero è pari a 30. Si tratta dell'impostazione predefinita globale e gli amministratori possono disabilitare la cronologia chat in base alla categoria.
    
     > [!IMPORTANT]
     > Il server Chat persistente memorizza nella cache questi messaggi nella cache, quindi se si aumenta questo numero, verranno memorizzati nella cache più messaggi. È sempre possibile accedere al contenuto cronologico eseguendo una ricerca. Il numero predefinito determina semplicemente il numero massimo di messaggi che verranno inizialmente visualizzati quando ci si connette a una chat room. 
  
   - In **Dimensioni massime file (KB)** selezionare la dimensione massima del file di ogni cronologia chat. Per impostazione predefinita, il numero è pari a 20 MB (20.000 KB). Si tratta della dimensione massima di un file caricabile in qualsiasi chat room (per cui sono abilitati i caricamenti di file mediante l'impostazione **Categoria** corrispondente) del sistema.
    
   - In **Limite di aggiornamento partecipanti** selezionare il limite per gli aggiornamenti dei partecipanti. Il server Chat persistente invia le informazioni dell'elenco (che è connesso a una chat room) a tutti i partecipanti fino a quando il numero di utenti connessi non raggiunge questo numero. Per impostazione predefinita, questo valore è pari a 75. Questo limite indica il numero massimo di partecipanti in una determinata sala oltre il quale il server Chat persistente smette di inviare aggiornamenti dell'elenco dei partecipanti ai client connessi su chi è presente nella sala.
    
   - Facoltativo. In **URL gestione sala** selezionare l'URL di gestione delle chat room. Si tratta dell'URL di una gestione chat room personalizzata basata sul Web. Se non è necessario personalizzare la gestione delle chat room e si usa semplicemente l'impostazione predefinita, lasciare vuota questa opzione. Dopo essere stato impostato, l'URL viene applicato come URL di gestione chat room interna ed esterna.
    
     Se si desidera personalizzare l'esperienza di creazione delle chat room e includere il flusso di lavoro aziendale specifico, è possibile creare una soluzione di gestione delle chat room personalizzata utilizzando il Software Development Kit (SDK) del server Chat persistente, ospitarla in un punto qualsiasi e inserire l'URL qui. Questo URL viene inviato al client, in modo tale che, quando un utente tenta di visualizzare o creare una chat, viene indirizzato alla soluzione di gestione chat personalizzata.
    
7. Fare clic su **Commit**.
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>Per configurare le opzioni di Persistent Chat per uno specifico pool di server Chat persistente

1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** seleziona il pannello Skype for Business Server o apri una finestra del browser e quindi immetti l'URL di amministratore.
    
3. Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Configurazione Persistent Chat**.
    
4. Nella pagina **Configurazione Persistent Chat** fare clic su **Nuovo** e quindi su **Configurazione pool**.
    
5. In **Selezionare un servizio** selezionare il servizio associato al pool di server Chat persistente da configurare.
    
6. In **Nuova configurazione Persistent Chat** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per le nuove impostazioni di configurazione. Per impostazione predefinita, il nome del pool del sito esiste già.
    
   - In **Cronologia chat predefinita** definire il numero di messaggi chat che verranno elaborati per ogni chat alla prima richiesta. Per impostazione predefinita, questo numero è pari a 30. Si tratta dell'impostazione predefinita globale e gli amministratori possono disabilitare la cronologia chat in base alla categoria.
    
     > [!IMPORTANT]
     > Il server Chat persistente memorizza nella cache questi messaggi nella cache, quindi se si aumenta questo numero, verranno memorizzati nella cache più messaggi. È sempre possibile accedere al contenuto cronologico eseguendo una ricerca. Il numero predefinito determina semplicemente il numero massimo di messaggi che verranno inizialmente visualizzati quando ci si connette a una chat room. 
  
   - In **Dimensioni massime file (KB)** selezionare la dimensione massima del file di ogni cronologia chat. Per impostazione predefinita, il numero è pari a 20 MB (20.000 KB). Si tratta della dimensione massima di un file caricabile in qualsiasi chat room (per cui sono abilitati i caricamenti di file mediante l'impostazione **Categoria** corrispondente) del sistema.
    
   - In **Limite di aggiornamento partecipanti** selezionare il limite per gli aggiornamenti dei partecipanti. Il server Chat persistente invia le informazioni dell'elenco (che è connesso a una chat room) a tutti i partecipanti fino a quando il numero di utenti connessi non raggiunge questo numero. Per impostazione predefinita, questo valore è pari a 75. Questo limite indica il numero massimo di partecipanti in una determinata sala oltre il quale il server Chat persistente smette di inviare aggiornamenti dell'elenco dei partecipanti ai client connessi su chi è presente nella sala.
    
   - In **URL gestione chat** selezionare l'URL di gestione chat. Si tratta dell'URL di una distribuzione di gestione chat basata sul Web. Se non è necessario personalizzare la gestione delle chat room e si usa semplicemente l'impostazione predefinita, lasciare vuota questa opzione.
    
     Se si desidera personalizzare l'esperienza di creazione delle chat room e includere il flusso di lavoro aziendale specifico, è possibile creare una soluzione di gestione delle chat room personalizzata utilizzando il Software Development Kit (SDK) del server Chat persistente, ospitarla in un punto qualsiasi e inserire l'URL qui. Questo URL viene inviato al client, in modo tale che, quando un utente tenta di visualizzare o creare una chat, viene indirizzato alla soluzione di gestione chat personalizzata.
    
7. Fare clic su **Commit**.
    
## <a name="see-also"></a>Vedere anche

Per informazioni dettagliate sulle funzionalità e sulle funzionalità del server Chat persistente, vedere [Plan for Persistent Chat Server in Skype for Business Server 2015,](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)Deploy Persistent Chat Server in Skype for Business Server [2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)e [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

