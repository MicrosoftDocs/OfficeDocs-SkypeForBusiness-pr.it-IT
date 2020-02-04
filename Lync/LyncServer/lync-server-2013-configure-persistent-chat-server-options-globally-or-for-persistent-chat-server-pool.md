---
title: 'Lync Server 2013: Configurare le opzioni del server chat persistente a livello globale o per il pool di server chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Persistent Chat Server options globally or for Persistent Chat Server pool
ms:assetid: 1e8d5245-cd58-4aad-9a1c-35b24189bc40
ms:mtpsurl: https://technet.microsoft.com/library/JJ204731(v=OCS.15)
ms:contentKeyID: 48183581
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86ee77dd34e3a43ea62ac6cffaf4af952b1c447e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a>Configurare le opzioni del server chat persistente a livello globale o per il pool di server chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-06_

Nel pannello di controllo di Lync Server 2013 è possibile usare la sezione configurazione della chat **persistente** della pagina della **chat** persistente per configurare le impostazioni della chat persistente a livello globale, dove si applica a tutti i pool di server di chat permanenti o per un pool di server di chat persistente specifico.

<div>


> [!NOTE]  
> Per configurare e usare il server di chat persistente, è necessario prima di tutto usare generatore di topologia per aggiungere il supporto del server di chat persistente alla topologia e quindi pubblicare la topologia. Per informazioni dettagliate, vedere <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">aggiunta di un server di chat persistente alla distribuzione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a>Per configurare le opzioni di chat persistenti a livello globale

1.  Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a un qualsiasi computer nella distribuzione interna.

2.  Nel menu **Start** selezionare il pannello di controllo di Lync Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > È anche possibile usare i cmdlet di Windows PowerShell. Per informazioni dettagliate, vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configurazione del server di chat persistente tramite i cmdlet di Windows PowerShell</A> nella documentazione relativa alla distribuzione.

    
    </div>

3.  Sulla barra di spostamento sinistra fare clic su **Chat persistente** e quindi su **Configurazione di Chat persistente**.

4.  Nella pagina di **configurazione della chat persistente** fare clic su **nuovo** e quindi su **configurazione sito**.
    
    <div>
    

    > [!IMPORTANT]  
    > Scegliere questa opzione se si vuole che la configurazione venga applicata a tutti i pool di server di chat persistenti distribuiti nel sito. Fare clic su <STRONG>Configurazione pool</STRONG> se si vuole che la configurazione venga applicata a un pool di server di chat persistente specifico.

    
    </div>

5.  In **Seleziona un sito**selezionare il sito da configurare per la configurazione del sito del server Chat persistente.

6.  In **Nuova configurazione di Chat persistente** eseguire le operazioni seguenti:
    
      - In **Nome** specificare un nome per le nuove impostazioni di configurazione. Per impostazione predefinita, il nome del sito esiste già.
    
      - In **Cronologia chat predefinita** definire il numero di messaggi chat che verranno elaborati per ogni chat room alla prima richiesta. Per impostazione predefinita, il numero è 30. Si tratta dell'impostazione globale predefinita e gli amministratori possono disabilitare la cronologia chat per categoria.
        
        <div>
        

        > [!IMPORTANT]  
        > Il server di chat persistente memorizza nella cache questi messaggi in memoria, quindi se si aumenta questo numero, verrà memorizzato nella cache altri messaggi. È sempre possibile accedere al contenuto cronologico tramite ricerca. Il numero predefinito determina semplicemente il numero massimo di messaggi visualizzati inizialmente alla connessione a una chat room.

        
        </div>
    
      - In **Dimensioni massime file (KB)** selezionare le dimensioni file massime di ogni cronologia chat. Per impostazione predefinita, il numero è 20 MB (20.000 KB). Si tratta delle dimensioni massime per un file caricabile in qualsiasi chat room nel sistema (per cui i caricamenti sono abilitati attraverso la relativa impostazione **Categoria**).
        
        <div>
        

        > [!IMPORTANT]  
        > Questa impostazione viene applicata nel server perché le applicazioni personalizzate o i client di chat di gruppo precedenti che usano Office Communications Server&nbsp;2007 R2 Group Chat Server o Lync Server 2010, Group Chat possono pubblicare file in una sala. Il client Lync 2013 non è in grado di caricare/scaricare file, quindi se si ha una distribuzione di Lync 2013 pura o un client Lync 2013, non è possibile pubblicare file in una chat room del server di chat persistente.

        
        </div>
    
      - In **Limite di aggiornamento partecipanti** selezionare il limite per gli aggiornamenti dei partecipanti. Il server di chat persistente invia le informazioni del roster (che sono connesse a una chat room) a tutti i partecipanti finché il numero di utenti connessi non raggiunge questo numero. Per impostazione predefinita, il numero è 75. Questo limite indica il numero massimo di partecipanti in una determinata sala oltre la quale il server di chat persistente smette di inviare aggiornamenti di Roster ai client connessi su chi è presente nella sala.
    
      - (Facoltativo.) In **URL gestione chat** selezionare l'URL di gestione della chat room. Si tratta dell'URL di una gestione chat room personalizzata basata sul Web. Se non è necessario personalizzare la gestione della chat room e si usa l'impostazione predefinita, non immettere alcun URL. Dopo essere stato impostato, l'URL viene applicato come URL di gestione chat room interna ed esterna.
        
        Se si vuole personalizzare l'esperienza di creazione di una sala e includere un flusso di lavoro aziendale specifico, è possibile creare una soluzione di gestione delle sale personalizzata usando il Software Development Kit (SDK) di Persistent Chat Server, ospitarlo da qualche parte e inserire l'URL qui. Questo URL viene inviato al client in modo che quando un utente tenta di visualizzare o creare una chat room, viene indirizzato alla soluzione di gestione personalizzata.

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>Per configurare le opzioni di chat persistenti per un pool di server di chat persistente specifico

1.  Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a un qualsiasi computer nella distribuzione interna.

2.  Nel menu **Start** selezionare il pannello di controllo di Lync Server oppure aprire una finestra del browser e quindi immettere l'URL dell'amministratore. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > È anche possibile usare i cmdlet di Windows PowerShell. Per informazioni dettagliate, vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configurazione del server di chat persistente tramite i cmdlet di Windows PowerShell</A> nella documentazione relativa alla distribuzione.

    
    </div>

3.  Sulla barra di spostamento sinistra fare clic su **Chat persistente** e quindi su **Configurazione di Chat persistente**.

4.  Nella pagina **Configurazione di Chat persistente** fare clic su **Nuovo** e quindi su **Configurazione pool**.

5.  In **Seleziona un servizio**selezionare il servizio associato al pool di server di chat persistente da configurare.

6.  In **Nuova configurazione di Chat persistente** eseguire le operazioni seguenti:
    
      - In **Nome** specificare un nome per le nuove impostazioni di configurazione. Per impostazione predefinita, il nome del pool esiste già.
    
      - In **Cronologia chat predefinita** definire il numero di messaggi chat che verranno elaborati per ogni chat room alla prima richiesta. Per impostazione predefinita, il numero è 30. Si tratta dell'impostazione globale predefinita e gli amministratori possono disabilitare la cronologia chat per categoria.
        
        <div>
        

        > [!IMPORTANT]  
        > Il server di chat persistente memorizza nella cache questi messaggi in memoria, quindi se si aumenta questo numero, verrà memorizzato nella cache altri messaggi. È sempre possibile accedere al contenuto cronologico tramite ricerca. Il numero predefinito determina semplicemente il numero massimo di messaggi visualizzati inizialmente alla connessione a una chat room.

        
        </div>
    
      - In **Dimensioni massime file (KB)** selezionare le dimensioni file massime di ogni cronologia chat. Per impostazione predefinita, il numero è 20 MB (20.000 KB). Si tratta delle dimensioni massime per un file caricabile in qualsiasi chat room nel sistema (per cui i caricamenti sono abilitati attraverso la relativa impostazione **Categoria**).
        
        <div>
        

        > [!IMPORTANT]  
        > Questa impostazione viene applicata nel server perché le applicazioni personalizzate o i client di chat di gruppo precedenti (Office Communications Server 2007&nbsp;R2 Group Chat Server o Lync Server 2010, Group Chat) possono pubblicare file in una sala. Il client Lync 2013 non è in grado di caricare/scaricare file, quindi se si ha una distribuzione di Lync 2013 pura o un client Lync 2013, non è possibile pubblicare file in una chat room del server di chat persistente.

        
        </div>
    
      - In **Limite di aggiornamento partecipanti** selezionare il limite per gli aggiornamenti dei partecipanti. Il server di chat persistente invia le informazioni del roster (che sono connesse a una chat room) a tutti i partecipanti finché il numero di utenti connessi non raggiunge questo numero. Per impostazione predefinita, il numero è 75. Questo limite indica il numero massimo di partecipanti in una determinata sala oltre la quale il server di chat persistente smette di inviare aggiornamenti di Roster ai client connessi su chi è presente nella sala.
    
      - In **URL gestione chat** selezionare l'URL di gestione della chat room. Si tratta dell'URL di una distribuzione di gestione chat room basata sul Web. Se non è necessario personalizzare la gestione della chat room e si usa l'impostazione predefinita, non immettere alcun URL.
        
        Se si vuole personalizzare l'esperienza di creazione di una sala e includere un flusso di lavoro aziendale specifico, è possibile creare una soluzione di gestione delle sale personalizzata usando il Software Development Kit (SDK) di Persistent Chat Server, ospitarlo da qualche parte e inserire l'URL qui. Questo URL viene inviato al client in modo che quando un utente tenta di visualizzare o creare una chat room, viene indirizzato alla soluzione di gestione personalizzata.

7.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

