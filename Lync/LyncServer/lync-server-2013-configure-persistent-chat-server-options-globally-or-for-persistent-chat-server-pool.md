---
title: 'Lync Server 2013: configurare le opzioni del server Chat persistente a livello globale o per il pool di server Chat persistente'
description: 'Lync Server 2013: configurare le opzioni del server Chat persistente a livello globale o per il pool di server Chat persistente.'
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
ms.openlocfilehash: 0e0e26fc8719f9aa5f153a7962df70ee7237b980
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564992"
---
# <a name="configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool-in-lync-server-2013"></a>Configurare le opzioni del server Chat persistente a livello globale o per il pool di server Chat persistente in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-06_

Nel pannello di controllo di Lync Server 2013, è possibile utilizzare la sezione **configurazione di Persistent Chat** della pagina **chat** persistente per configurare le impostazioni di chat persistente a livello globale in cui si applica a tutti i pool di server Chat persistente o per un pool di server Chat persistente specifico.

<div>


> [!NOTE]  
> Per configurare e utilizzare il server Chat persistente, è necessario innanzitutto utilizzare Generatore di topologie per aggiungere il supporto del server Chat persistente alla topologia e quindi pubblicare la topologia. Per ulteriori informazioni, vedere <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">aggiunta del server Chat persistente alla distribuzione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="to-configure-persistent-chat-options-globally"></a>Per configurare le opzioni di chat persistente a livello globale

1.  Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Dal menu **Start** selezionare il pannello di controllo di Lync Server o aprire una finestra del browser e quindi immettere l'URL di amministratore. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > È inoltre possibile utilizzare i cmdlet di Windows PowerShell. Per informazioni dettagliate, vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> nella documentazione relativa alla distribuzione.

    
    </div>

3.  Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Configurazione Persistent Chat**.

4.  Nella pagina **Configurazione Persistent Chat** fare clic su **nuovo** e quindi su **configurazione sito**.
    
    <div>
    

    > [!IMPORTANT]  
    > Scegliere questa opzione se si desidera che la configurazione venga applicata a tutti i pool di server Chat persistente distribuiti nel sito. Fare clic su <STRONG>Configurazione pool</STRONG> se si desidera che la configurazione venga applicata a un pool di server Chat persistente specifico.

    
    </div>

5.  In **Seleziona un sito**selezionare il sito da configurare per la configurazione del sito del server Chat persistente.

6.  In **Nuova configurazione Persistent Chat** eseguire le operazioni seguenti:
    
      - In **Nome** specificare un nome per le nuove impostazioni di configurazione. Per impostazione predefinita, il nome del sito esiste già.
    
      - In **Cronologia chat predefinita** definire il numero di messaggi chat che verranno elaborati per ogni chat alla prima richiesta. Per impostazione predefinita, questo numero è pari a 30. Si tratta dell'impostazione predefinita globale e gli amministratori possono disabilitare la cronologia chat in base alla categoria.
        
        <div>
        

        > [!IMPORTANT]  
        > Il server Chat persistente memorizza nella cache questi messaggi in memoria, quindi se si aumenta questo numero, più messaggi verranno memorizzati nella cache. È sempre possibile accedere al contenuto cronologico eseguendo una ricerca. Il numero predefinito determina semplicemente il numero massimo di messaggi che verranno inizialmente visualizzati quando ci si connette a una chat room.

        
        </div>
    
      - In **Dimensioni massime file (KB)** selezionare la dimensione massima del file di ogni cronologia chat. Per impostazione predefinita, il numero è pari a 20 MB (20.000 KB). Si tratta della dimensione massima di un file caricabile in qualsiasi chat room (per cui sono abilitati i caricamenti di file mediante l'impostazione **Categoria** corrispondente) del sistema.
        
        <div>
        

        > [!IMPORTANT]  
        > Questa impostazione viene applicata sul server perché le applicazioni personalizzate o i client di chat di gruppo precedenti che utilizzano Office Communications Server 2007 R2 &nbsp; Group Chat Server o Lync server 2010, Group Chat possono inserire file in una sala. Il client Lync 2013 non dispone di funzionalità di caricamento e download dei file, pertanto se si dispone di una distribuzione di Lync 2013 pura o di un client Lync 2013, non è possibile inserire file in una chat room del server di chat persistente.

        
        </div>
    
      - In **Limite di aggiornamento partecipanti** selezionare il limite per gli aggiornamenti dei partecipanti. Il server Chat persistente invia informazioni roster (che sono connessi a una chat room) a tutti i partecipanti fino a quando il numero di utenti connessi raggiunge questo numero. Per impostazione predefinita, questo valore è pari a 75. Questo limite indica il numero massimo di partecipanti in una determinata sala oltre il quale il server Chat persistente interrompe l'invio degli aggiornamenti del roster ai client connessi su chi è presente nella sala.
    
      - (Facoltativo) In **URL gestione chat** selezionare l'URL di gestione chat. Si tratta dell'URL per una gestione chat personalizzata basata sul Web. Se non è necessario personalizzare la gestione chat, e si utilizza semplicemente l'impostazione predefinita, lasciare vuota questa opzione. Dopo l'impostazione, l'URL viene applicato come URL di gestione chat interno ed esterno.
        
        Se si desidera personalizzare l'esperienza di creazione della sala e includere il flusso di lavoro aziendale specifico, è possibile creare una soluzione di gestione della sala personalizzata utilizzando il Software Development Kit (SDK) di Persistent Chat Server, ospitarla da qualche parte e inserire l'URL. Questo URL viene inviato al client, in modo tale che, quando un utente tenta di visualizzare o creare una chat, viene indirizzato alla soluzione di gestione chat personalizzata.

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a>Per configurare le opzioni di chat persistente per un pool di server Chat persistente specifico

1.  Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Scegliere il pannello di controllo di Lync Server dal menu **Start** oppure aprire una finestra del browser e quindi immettere l'URL di amministratore. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > È inoltre possibile utilizzare i cmdlet di Windows PowerShell. Per informazioni dettagliate, vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> nella documentazione relativa alla distribuzione.

    
    </div>

3.  Sulla barra di spostamento sinistra fare clic su **Persistent Chat** e quindi su **Configurazione Persistent Chat**.

4.  Nella pagina **Configurazione Persistent Chat** fare clic su **Nuovo** e quindi su **Configurazione pool**.

5.  In **Seleziona un servizio**selezionare il servizio associato al pool di server Chat persistente da configurare.

6.  In **Nuova configurazione Persistent Chat** eseguire le operazioni seguenti:
    
      - In **Nome** specificare un nome per le nuove impostazioni di configurazione. Per impostazione predefinita, il nome del pool del sito esiste già.
    
      - In **Cronologia chat predefinita** definire il numero di messaggi chat che verranno elaborati per ogni chat alla prima richiesta. Per impostazione predefinita, questo numero è pari a 30. Si tratta dell'impostazione predefinita globale e gli amministratori possono disabilitare la cronologia chat in base alla categoria.
        
        <div>
        

        > [!IMPORTANT]  
        > Il server Chat persistente memorizza nella cache questi messaggi in memoria, quindi se si aumenta questo numero, più messaggi verranno memorizzati nella cache. È sempre possibile accedere al contenuto cronologico eseguendo una ricerca. Il numero predefinito determina semplicemente il numero massimo di messaggi che verranno inizialmente visualizzati quando ci si connette a una chat room.

        
        </div>
    
      - In **Dimensioni massime file (KB)** selezionare la dimensione massima del file di ogni cronologia chat. Per impostazione predefinita, il numero è pari a 20 MB (20.000 KB). Si tratta della dimensione massima di un file caricabile in qualsiasi chat room (per cui sono abilitati i caricamenti di file mediante l'impostazione **Categoria** corrispondente) del sistema.
        
        <div>
        

        > [!IMPORTANT]  
        > Questa impostazione viene applicata sul server perché le applicazioni personalizzate o i client di chat di gruppo precedenti (Office Communications Server 2007 R2 &nbsp; Group Chat Server o Lync server 2010, Group Chat) possono inserire file in una sala. Il client Lync 2013 non dispone di funzionalità di caricamento e download dei file, pertanto se si dispone di una distribuzione di Lync 2013 pura o di un client Lync 2013, non è possibile inserire file in una chat room del server di chat persistente.

        
        </div>
    
      - In **Limite di aggiornamento partecipanti** selezionare il limite per gli aggiornamenti dei partecipanti. Il server Chat persistente invia informazioni roster (che sono connessi a una chat room) a tutti i partecipanti fino a quando il numero di utenti connessi raggiunge questo numero. Per impostazione predefinita, questo valore è pari a 75. Questo limite indica il numero massimo di partecipanti in una determinata sala oltre il quale il server Chat persistente interrompe l'invio degli aggiornamenti del roster ai client connessi su chi è presente nella sala.
    
      - In **URL gestione chat** selezionare l'URL di gestione della chat room. Si tratta dell'URL di una distribuzione di gestione chat room basata sul Web. Se non è necessario personalizzare la gestione della chat room e si usa l'impostazione predefinita, non immettere alcun URL.
        
        Se si desidera personalizzare l'esperienza di creazione della sala e includere il flusso di lavoro aziendale specifico, è possibile creare una soluzione di gestione della sala personalizzata utilizzando il Software Development Kit (SDK) di Persistent Chat Server, ospitarla da qualche parte e inserire l'URL. Questo URL viene inviato al client in modo che quando un utente tenta di visualizzare o creare una chat room, viene indirizzato alla soluzione di gestione personalizzata.

7.  Fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

