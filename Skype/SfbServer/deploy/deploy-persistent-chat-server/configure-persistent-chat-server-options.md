---
title: Configurare le opzioni del server Chat persistente in Skype for Business Server 2015
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
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a>Configurare le opzioni del server Chat persistente in Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come configurare le opzioni del server Chat persistente a livello globale, di sito o di pool in Skype for Business Server 2015.
  
È possibile specificare diverse opzioni per il server Chat persistente che può essere applicato a livello globale, a tutti i pool all'interno di un sito o a un pool specifico all'interno di un sito. Le opzioni del server Chat persistente sono le seguenti: 
  
- Cronologia chat predefinita. Il numero di messaggi chat disponibili per ogni chat room al primo richiesta. Il valore predefinito globale è 30 messaggi di chat. 
    
- Dimensioni massime dei file. Dimensioni massime di un file che è possibile caricare o scaricare da una chat room. L'impostazione predefinita globale è 20MB.
    
- Limite di aggiornamento dei partecipanti. Il numero massimo di partecipanti in una determinata chat room per la quale Persistent Chat invierà gli aggiornamenti del roster. L'impostazione predefinita globale è 75.
    
- URL di gestione della sala. URL utilizzato per la gestione delle chat room personalizzata. L'impostazione consente l'utilizzo di una soluzione di gestione della sala personalizzata. 
   
> [!NOTE] 
> La chat persistente è disponibile in Skype for Business Server 2015 ma non è più supportata in Skype for Business Server 2019. La stessa funzionalità è disponibile in teams. Per ulteriori informazioni, vedere [Guida introduttiva all'aggiornamento di Microsoft teams](/microsoftteams/upgrade-start-here). Se è necessario utilizzare la chat persistente, è possibile eseguire la migrazione degli utenti che richiedono questa funzionalità ai team oppure continuare a utilizzare Skype for Business Server 2015.
 
## <a name="configure-persistent-chat-server-global-options"></a>Configurare le opzioni globali del server Chat persistente

Per configurare le opzioni globali del server Chat persistente:
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL di amministratore.
    
3. Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Configurazione Persistent Chat**.
    
4. Nella pagina **Configurazione Persistent Chat** fare clic su **nuovo** e quindi su **configurazione sito**.
    
    > [!IMPORTANT]
    > Scegliere questa opzione se si desidera che la configurazione venga applicata a tutti i pool di server Chat persistente distribuiti nel sito. Fare clic su **Configurazione pool** se si desidera che la configurazione venga applicata a un pool di server Chat persistente specifico.
  
5. In **Seleziona un sito** selezionare il sito da configurare per la configurazione del sito del server Chat persistente.
    
6. In **Nuova configurazione Persistent Chat** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per le nuove impostazioni di configurazione. Per impostazione predefinita, il nome del sito esiste già.
    
   - In **Cronologia chat predefinita** definire il numero di messaggi chat che verranno elaborati per ogni chat alla prima richiesta. Per impostazione predefinita, questo numero è pari a 30. Si tratta dell'impostazione predefinita globale e gli amministratori possono disabilitare la cronologia chat in base alla categoria.
    
     > [!IMPORTANT]
     > Il server Chat persistente memorizza nella cache questi messaggi in memoria, quindi se si aumenta questo numero, più messaggi verranno memorizzati nella cache. È sempre possibile accedere al contenuto cronologico eseguendo una ricerca. Il numero predefinito determina semplicemente il numero massimo di messaggi che verranno inizialmente visualizzati quando ci si connette a una chat room. 
  
   - In **Dimensioni massime file (KB)** selezionare la dimensione massima del file di ogni cronologia chat. Per impostazione predefinita, il numero è pari a 20 MB (20.000 KB). Si tratta della dimensione massima di un file caricabile in qualsiasi chat room (per cui sono abilitati i caricamenti di file mediante l'impostazione **Categoria** corrispondente) del sistema.
    
   - In **Limite di aggiornamento partecipanti** selezionare il limite per gli aggiornamenti dei partecipanti. Il server Chat persistente invia informazioni roster (che sono connessi a una chat room) a tutti i partecipanti fino a quando il numero di utenti connessi raggiunge questo numero. Per impostazione predefinita, questo valore è pari a 75. Questo limite indica il numero massimo di partecipanti in una determinata sala oltre il quale il server Chat persistente interrompe l'invio degli aggiornamenti del roster ai client connessi su chi è presente nella sala.
    
   - (Facoltativo.) In **URL gestione chat** selezionare l'URL di gestione della sala. Si tratta dell'URL di una gestione chat room personalizzata basata sul Web. Se non è necessario personalizzare la gestione delle sale e si utilizza semplicemente l'impostazione predefinita, lasciare vuota questa opzione. Dopo essere stato impostato, l'URL viene applicato come URL di gestione chat room interna ed esterna.
    
     Se si desidera personalizzare l'esperienza di creazione della sala e includere il flusso di lavoro aziendale specifico, è possibile creare una soluzione di gestione della sala personalizzata utilizzando il Software Development Kit (SDK) di Persistent Chat Server, ospitarla da qualche parte e inserire l'URL. Questo URL viene inviato al client, in modo tale che, quando un utente tenta di visualizzare o creare una chat, viene indirizzato alla soluzione di gestione chat personalizzata.
    
7. Fare clic su **Commit**.
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a>Configurare le opzioni per un pool di server Chat persistente specifico

Per configurare le opzioni per un pool di server Chat persistente specifico.
  
1. Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.
    
2. Dal menu **Start** selezionare il pannello di controllo di Skype for Business Server o aprire una finestra del browser e quindi immettere l'URL di amministratore.
    
3. Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Configurazione Persistent Chat**.
    
4. Nella pagina **Configurazione Persistent Chat** fare clic su **Nuovo** e quindi su **Configurazione pool**.
    
5. In **Seleziona un servizio** selezionare il servizio associato al pool di server Chat persistente da configurare.
    
6. In **Nuova configurazione Persistent Chat** eseguire le operazioni seguenti:
    
   - In **Nome** specificare un nome per le nuove impostazioni di configurazione. Per impostazione predefinita, il nome del pool del sito esiste già.
    
   - In **Cronologia chat predefinita** definire il numero di messaggi chat che verranno elaborati per ogni chat alla prima richiesta. Per impostazione predefinita, questo numero è pari a 30. Si tratta dell'impostazione predefinita globale e gli amministratori possono disabilitare la cronologia chat in base alla categoria.
    
     > [!IMPORTANT]
     > Il server Chat persistente memorizza nella cache questi messaggi in memoria, quindi se si aumenta questo numero, più messaggi verranno memorizzati nella cache. È sempre possibile accedere al contenuto cronologico eseguendo una ricerca. Il numero predefinito determina semplicemente il numero massimo di messaggi che verranno inizialmente visualizzati quando ci si connette a una chat room. 
  
   - In **Dimensioni massime file (KB)** selezionare la dimensione massima del file di ogni cronologia chat. Per impostazione predefinita, il numero è pari a 20 MB (20.000 KB). Si tratta della dimensione massima di un file caricabile in qualsiasi chat room (per cui sono abilitati i caricamenti di file mediante l'impostazione **Categoria** corrispondente) del sistema.
    
   - In **Limite di aggiornamento partecipanti** selezionare il limite per gli aggiornamenti dei partecipanti. Il server Chat persistente invia informazioni roster (che sono connessi a una chat room) a tutti i partecipanti fino a quando il numero di utenti connessi raggiunge questo numero. Per impostazione predefinita, questo valore è pari a 75. Questo limite indica il numero massimo di partecipanti in una determinata sala oltre il quale il server Chat persistente interrompe l'invio degli aggiornamenti del roster ai client connessi su chi è presente nella sala.
    
   - In **URL gestione chat** selezionare l'URL di gestione della chat room. Si tratta dell'URL di una distribuzione di gestione chat basata sul Web. Se non è necessario personalizzare la gestione delle sale e si utilizza semplicemente l'impostazione predefinita, lasciare vuota questa opzione.
    
     Se si desidera personalizzare l'esperienza di creazione della sala e includere il flusso di lavoro aziendale specifico, è possibile creare una soluzione di gestione della sala personalizzata utilizzando il Software Development Kit (SDK) di Persistent Chat Server, ospitarla da qualche parte e inserire l'URL. Questo URL viene inviato al client in modo che quando un utente tenta di visualizzare o creare una chat room, viene indirizzato alla soluzione di gestione personalizzata.
    
7. Fare clic su **Commit**.
    

