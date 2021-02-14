---
title: Configurare le opzioni del server Chat persistente in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: 'Riepilogo: informazioni su come configurare le opzioni del server Chat persistente a livello globale, di sito o di pool in Skype for Business Server 2015.'
ms.openlocfilehash: 9c0b6d5e03b9bc4f7d955ea0dae3e1c45b14ada3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802126"
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a>Configurare le opzioni del server Chat persistente in Skype for Business Server
 
**Riepilogo:** Informazioni su come configurare le opzioni del server Chat persistente a livello globale, di sito o di pool in Skype for Business Server 2015.
  
È possibile specificare diverse opzioni per il server Chat persistente che è possibile applicare a livello globale, a tutti i pool all'interno di un sito o a un pool specifico all'interno di un sito. Le opzioni del server Chat persistente includono: 
  
- Cronologia chat predefinita. Numero di messaggi di chat disponibili per ogni chat room alla prima richiesta. Il valore predefinito globale è 30 messaggi di chat. 
    
- Dimensioni massime file. La dimensione massima di un file che può essere caricato o scaricato da una chat room. Il valore predefinito globale è 20 MB.
    
- Limite di aggiornamento dei partecipanti. Numero massimo di partecipanti in una determinata chat room per cui Persistent Chat invierà gli aggiornamenti dell'elenco. Il valore predefinito globale è 75.
    
- URL gestione chat room. URL utilizzato per la gestione personalizzata delle chat room. L'impostazione consente l'utilizzo di una soluzione di gestione chat personalizzata. 
   
> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015, ma non è più supportata in Skype for Business Server 2019. Le stesse funzionalità sono disponibili in Teams. Per altre informazioni, vedere [Introduzione all'aggiornamento di Microsoft Teams.](/microsoftteams/upgrade-start-here) Se è necessario usare Chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità a Teams o continuare a usare Skype for Business Server 2015.
 
## <a name="configure-persistent-chat-server-global-options"></a>Configurare le opzioni globali del server Chat persistente

Per configurare le opzioni globali del server Chat persistente:
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** seleziona il Pannello di controllo di Skype for Business Server o apri una finestra del browser e quindi immetti l'URL di amministrazione.
    
3. Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Configurazione Persistent Chat**.
    
4. Nella pagina **Configurazione chat persistente** fare clic su **Nuovo e** quindi su **Configurazione sito.**
    
    > [!IMPORTANT]
    > Scegliere questa opzione se si desidera applicare la configurazione a tutti i pool di server Chat persistente distribuiti nel sito. Fare **clic su Configurazione** pool se si desidera applicare la configurazione a uno specifico pool di server Chat persistente.
  
5. In **Selezionare un sito** selezionare il sito da configurare per la configurazione del sito del server Chat persistente.
    
6. In **Nuova configurazione Persistent Chat** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per le nuove impostazioni di configurazione. Per impostazione predefinita, il nome del sito esiste già.
    
   - In **Cronologia chat predefinita** definire il numero di messaggi chat che verranno elaborati per ogni chat alla prima richiesta. Per impostazione predefinita, questo numero è pari a 30. Si tratta dell'impostazione predefinita globale e gli amministratori possono disabilitare la cronologia chat in base alla categoria.
    
     > [!IMPORTANT]
     > Il server Chat persistente memorizza questi messaggi nella cache, quindi se si aumenta questo numero, verranno memorizzati più messaggi nella cache. È sempre possibile accedere al contenuto cronologico eseguendo una ricerca. Il numero predefinito determina semplicemente il numero massimo di messaggi che verranno inizialmente visualizzati quando ci si connette a una chat room. 
  
   - In **Dimensioni massime file (KB)** selezionare la dimensione massima del file di ogni cronologia chat. Per impostazione predefinita, il numero è pari a 20 MB (20.000 KB). Si tratta della dimensione massima di un file caricabile in qualsiasi chat room (per cui sono abilitati i caricamenti di file mediante l'impostazione **Categoria** corrispondente) del sistema.
    
   - In **Limite di aggiornamento partecipanti** selezionare il limite per gli aggiornamenti dei partecipanti. Il server Chat persistente invia a tutti i partecipanti le informazioni sull'elenco degli utenti connessi a una chat room fino a quando il numero di utenti connessi non raggiunge questo numero. Per impostazione predefinita, questo valore è pari a 75. Questo limite indica il numero massimo di partecipanti in una determinata chat room oltre il quale il server Chat persistente smette di inviare aggiornamenti dell'elenco dei partecipanti ai client connessi su chi è presente nella sala.
    
   - (Facoltativo). In **URL gestione chat** selezionare l'URL di gestione chat room. Si tratta dell'URL di una gestione chat room personalizzata basata sul Web. Se non è necessario personalizzare la gestione delle chat room e si usa semplicemente l'impostazione predefinita, lasciare vuota questa opzione. Dopo essere stato impostato, l'URL viene applicato come URL di gestione chat room interna ed esterna.
    
     Se si desidera personalizzare l'esperienza di creazione della chat room e includere il flusso di lavoro aziendale specifico, è possibile creare una soluzione di gestione chat room personalizzata utilizzando Il Software Development Kit (SDK) del server Chat persistente, ospitarla in un percorso e inserire l'URL qui. Questo URL viene inviato al client, in modo tale che, quando un utente tenta di visualizzare o creare una chat, viene indirizzato alla soluzione di gestione chat personalizzata.
    
7. Fare clic su **Commit**.
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a>Configurare le opzioni per un pool di server Chat persistente specifico

Per configurare le opzioni per uno specifico pool di server Chat persistente.
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** seleziona il Pannello di controllo di Skype for Business Server oppure apri una finestra del browser e quindi immetti l'URL di amministrazione.
    
3. Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Configurazione Persistent Chat**.
    
4. Nella pagina **Configurazione Persistent Chat** fare clic su **Nuovo** e quindi su **Configurazione pool**.
    
5. In **Selezionare un servizio** selezionare il servizio associato al pool di server Chat persistente da configurare.
    
6. In **Nuova configurazione Persistent Chat** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per le nuove impostazioni di configurazione. Per impostazione predefinita, il nome del pool del sito esiste già.
    
   - In **Cronologia chat predefinita** definire il numero di messaggi chat che verranno elaborati per ogni chat alla prima richiesta. Per impostazione predefinita, questo numero è pari a 30. Si tratta dell'impostazione predefinita globale e gli amministratori possono disabilitare la cronologia chat in base alla categoria.
    
     > [!IMPORTANT]
     > Il server Chat persistente memorizza questi messaggi nella cache, quindi se si aumenta questo numero, verranno memorizzati più messaggi nella cache. È sempre possibile accedere al contenuto cronologico eseguendo una ricerca. Il numero predefinito determina semplicemente il numero massimo di messaggi che verranno inizialmente visualizzati quando ci si connette a una chat room. 
  
   - In **Dimensioni massime file (KB)** selezionare la dimensione massima del file di ogni cronologia chat. Per impostazione predefinita, il numero è pari a 20 MB (20.000 KB). Si tratta della dimensione massima di un file caricabile in qualsiasi chat room (per cui sono abilitati i caricamenti di file mediante l'impostazione **Categoria** corrispondente) del sistema.
    
   - In **Limite di aggiornamento partecipanti** selezionare il limite per gli aggiornamenti dei partecipanti. Il server Chat persistente invia a tutti i partecipanti le informazioni sull'elenco degli utenti connessi a una chat room fino a quando il numero di utenti connessi non raggiunge questo numero. Per impostazione predefinita, questo valore è pari a 75. Questo limite indica il numero massimo di partecipanti in una determinata chat room oltre il quale il server Chat persistente smette di inviare aggiornamenti dell'elenco dei partecipanti ai client connessi su chi è presente nella sala.
    
   - In **URL gestione chat** selezionare l'URL di gestione della chat room. Si tratta dell'URL di una distribuzione di gestione chat basata sul Web. Se non è necessario personalizzare la gestione delle chat room e si usa semplicemente l'impostazione predefinita, lasciare vuota questa opzione.
    
     Se si desidera personalizzare l'esperienza di creazione della chat room e includere il flusso di lavoro aziendale specifico, è possibile creare una soluzione di gestione chat room personalizzata utilizzando Il Software Development Kit (SDK) del server Chat persistente, ospitarla in un percorso e inserire l'URL qui. Questo URL viene inviato al client in modo che quando un utente tenta di visualizzare o creare una chat room, viene indirizzato alla soluzione di gestione personalizzata.
    
7. Fare clic su **Commit**.
    

