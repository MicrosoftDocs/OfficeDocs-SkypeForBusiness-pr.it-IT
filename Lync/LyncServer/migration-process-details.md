---
title: Processo di migrazione-Dettagli
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8a5e0ec0ab94dcba48917338f130b5de1a98f91
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a>Processo di migrazione-Dettagli

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

Utilizzare i prerequisiti seguenti e i passaggi dettagliati per eseguire la migrazione di Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat in Lync Server 2013, Persistent Chat Server.

<div>

## <a name="prerequisites-for-migration"></a>Prerequisiti per la migrazione

Assicurarsi di aver soddisfatto i prerequisiti seguenti prima di eseguire la migrazione di Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat a Lync Server 2013, server Chat persistente.

1.  Distribuire almeno un pool di Lync Server 2013. Se si dispone di più pool di Lync Server 2013, decidere quale pool di Lync Server 2013 sarà il pool Home per il nuovo pool di server Chat persistente di Lync Server 2013.

2.  Installare il pool di server Chat persistente di Lync Server 2013. Sarà vuoto (nessuna categoria, stanza o componente aggiuntivo). Prima di eseguire la migrazione delle categorie, delle sale o dei componenti aggiuntivi legacy, è possibile creare sale, categorie o componenti aggiuntivi nella distribuzione di server Chat persistente in Lync Server 2013.
    
    <div>
    

    > [!IMPORTANT]  
    > Tenere presente che questi elementi appena creati possono essere in conflitto con gli elementi legacy di cui si esegue la migrazione. Evitare conflitti di denominazione. in caso contrario, verranno sovrascritti quando si esegue la migrazione dei dati legacy.

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a>Preparazione dei dati di origine per la migrazione

Eseguire la procedura seguente per preparare correttamente i dati di origine per la migrazione.

1.  Eseguire il backup dei database di origine per Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat. Per informazioni dettagliate sul backup di SQL Server, vedere "Panoramica del backup (SQL Server)" <http://go.microsoft.com/fwlink/p/?linkid=254851>all'indirizzo.
    
    <div>
    

    > [!IMPORTANT]  
    > I servizi di dominio Active Directory devono essere uguali. Come condizione per la migrazione, non è possibile eseguire la migrazione a un pool in una distribuzione diversa, in particolare in una foresta di Active Directory diversa.

    
    </div>

2.  Esaminare le chat room e la configurazione delle categorie di Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat. Tutte le modifiche apportate alle categorie, alle sale o ai componenti aggiuntivi della distribuzione legacy esistente verranno eseguite dallo strumento di amministrazione di Group Chat.
    
    <div>
    

    > [!TIP]  
    > Tutte le modifiche apportate alle categorie, alle sale o ai componenti aggiuntivi di Lync Server 2013, la distribuzione del server Chat persistente vengono eseguite dal pannello di controllo di Lync Server o dai cmdlet di Windows PowerShell.

    
    </div>
    
    Eseguire la procedura seguente per preparare il sistema legacy per la migrazione.
    
    1.  Il server Chat persistente supporta un singolo livello di categorie, a differenza di un insieme gerarchico di categorie. Dopo la migrazione, le sottocategorie sono prefissate con nomi di categoria completi padre. Potrebbe essere necessario semplificare e appiattire la struttura delle categorie esistente in modo che la struttura risultante soddisfi i requisiti.
    
    2.  Verificare i **responsabili** nella categoria radice. Se esistono Manager a questo livello, tali utenti verranno aggiunti come **Manager a tutte le sale** dopo la migrazione. Se non si tratta di un requisito per l'organizzazione, è necessario rimuovere questi Manager dalla categoria radice.
    
    3.  Verificare la lunghezza dei nomi delle chat. Dopo la migrazione, a causa di strutture di categoria semplificate, se le camere sono presenti in una categoria figlio, sono preceduti da nomi di categoria completi padre. Il limite di denominazione è 256 caratteri, inclusi i nomi delle categorie padre. Se è troppo lungo, è necessario verificare la lunghezza dei nomi delle sale e possibilmente accorciare la lunghezza.
    
    4.  In Lync Server 2013, se le impostazioni per gli **inviti** di categoria sono impostate su true, è possibile scegliere True o false per gli inviti alle chat room della categoria. Tuttavia, se le impostazioni per gli inviti di categoria sono impostate su false, le sale di quella categoria dispongono di inviti disattivati. Prima di eseguire la migrazione, è necessario reimpostare le impostazioni degli inviti nella versione legacy di Lync Server Group Chat Server, se si desidera che le sale siano presenti in una categoria specifica. In caso contrario, durante la migrazione, Lync Server 2013 Visualizza gli avvisi e imposta le sale sul valore predefinito false.
    
    5.  Se sono stati utilizzati file nelle chat room, è necessario eseguire il XCOPY dei file manualmente nel nuovo archivio file di Persistent Chat dopo la migrazione. Gli strumenti non lo fanno.
    
    6.  Se si disponeva di utenti federati e di stanze con utenti federati, tenere presente che il server Chat persistente non supporta la Federazione. Verrà eseguita la migrazione delle sale con gli utenti federati. Tuttavia, gli utenti stessi non saranno in grado di accedere al contenuto, perché l'accesso federato non è supportato.
    
    7.  Identificare le sale di cui non si desidera eseguire la migrazione e contrassegnarle come disabilitate.
    
    8.  Identificare la data oltre la quale si desidera eseguire la migrazione del contenuto della chat room. Ad esempio, potrebbe non essere necessario eseguire la migrazione dei messaggi prima del 1 ° gennaio 2010, in quanto questi messaggi possono essere obsoleti o non rilevanti per la migrazione.

</div>

<div>

## <a name="performing-the-migration"></a>Esecuzione della migrazione

Eseguire la procedura seguente per eseguire la migrazione del server di chat di gruppo legacy.

1.  Arrestare i servizi server Chat persistente di Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat o Lync Server 2013. Tutti i servizi devono essere interrotti, quindi pianificare l'operazione in un momento in cui il tempo di inattività è sufficiente. Come descritto in precedenza, assicurarsi di eseguire il backup del database di Group Chat corrente.

2.  Eseguire il cmdlet **Export-CsPersistentChatData** di Windows PowerShell come membro del ruolo di amministratore RBAC di Persistent Chat (ruolo CsPersistentChatAdministrator). Per informazioni dettagliate sui cmdlet per l'esportazione e l'importazione, vedere [risoluzione dei problemi relativi alla configurazione del server Chat persistente tramite i cmdlet di Windows PowerShell in Lync server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).
    
    Esaminare il contenuto esportato.

3.  Prima di essere pronti per l'importazione, arrestare Lync Server 2013, servizi del server Chat persistente. Tutti i servizi devono essere interrotti, quindi pianificare l'operazione in un momento in cui il tempo di inattività è sufficiente.

4.  Eseguire un backup del database di Persistent Chat se sono state create categorie, sale o componenti aggiuntivi nella distribuzione di Lync Server 2013 prima della migrazione. Il processo di esportazione/importazione sarà in grado di unire i dati legacy nella distribuzione di Lync Server 2013, ma è consigliabile eseguire il backup del database nel caso in cui il contenuto venga inavvertitamente sovrascritto (ad esempio, se esistono ancora conflitti di denominazione).

5.  Eseguire il cmdlet **Import-CsPersistentChatData** di Windows PowerShell (strumento di importazione), con un comando **whatIf** per popolare il server back-end del pool di server Chat persistente con i dati migrati. Alcune conversioni si verificano nel processo per ospitare il modello di amministrazione semplificato. Consente di risolvere eventuali errori o avvisi visualizzati.

6.  Eseguire il cmdlet **Import-CsPersistentChatData** di Windows PowerShell per il server di chat persistente come membro del ruolo RBAC (ruolo CsPersistentChatAdministrator) Administrator di Persistent Chat. Per informazioni dettagliate sui cmdlet per l'esportazione e l'importazione, vedere [risoluzione dei problemi relativi alla configurazione del server Chat persistente tramite i cmdlet di Windows PowerShell in Lync server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).

7.  È necessario XCOPY tutti i file caricati (l'intera cartella) nel nuovo archivio file di Lync Server 2013, Persistent Chat.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync 2013 (client) non supporta il caricamento o la visualizzazione di file nelle chat room. È comunque possibile utilizzare il client legacy per inserire e visualizzare i file nella sala.

    
    </div>

8.  Porta l'URI del server di ricerca di Microsoft Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat all'oggetto contatto del server di chat persistente di Lync 2013 server. I passaggi seguenti sono obbligatori se i client di chat di gruppo di Lync 2010 o di Office Communicator 2007 R2 devono connettersi all'ultima Lync 2013, Persistent Chat (client) dopo la migrazione senza modifiche alla configurazione sul fianco del client:
    
      - Eliminare l'account\<utente del\>Server di ricerca di OCSChat@ domainname. com. Questo è stato utilizzato per puntare al servizio di ricerca in Lync Server 2010, Group Chat. È possibile disinstallare il pool e rimuovere le voci attendibili in un secondo momento.
    
      - Creare un endpoint legacy (oggetto contatto del server Chat persistente) eseguendo il cmdlet di Windows PowerShell **New-CsPersistentChatEndpoint**con l'URI SIP identico in modo che il client legacy funzioni efficacemente quando il servizio viene riavviato.
    
    Il processo di migrazione obbligatoria è stato completato a questo punto. Lync 2010 Group Chat (clients) o Office Communicator 2007 R2 Group Chat (client) è in grado di connettersi al nuovo pool di server Chat persistente ora, in modo trasparente.
    
    Seguire questi passaggi aggiuntivi per la rimozione delle autorizzazioni per Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat.

9.  Avviare i servizi del server Chat persistente attivando tutti i computer nel nuovo pool di server Chat persistente.

10. Utilizzare il pannello di controllo di Lync Server e i cmdlet di Windows PowerShell per verificare che i dati siano stati migrati correttamente.

11. Disinstallare Lync 2010 Group Chat o Office Communicator 2007 R2 Group Chat dai computer del pool di Group Chat Server.

12. Eliminare l'applicazione attendibile e il pool di applicazioni attendibili utilizzando i cmdlet di Windows PowerShell. Questo elimina gli elementi dall'archivio di gestione centrale e dalle voci del servizio attendibili associate (TSE) da Active Directory. In alternativa, questo passaggio è compatibile con il generatore di topologie (anche le applicazioni o i pool attendibili dispongono di un nodo dedicato).

13. È ora possibile iniziare a abilitare la funzionalità del server Chat persistente tramite i nuovi client. Per informazioni dettagliate sull'abilitazione del server Chat persistente, vedere [Deploying Persistent Chat Server in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 supporta più pool di server Chat persistente. Tuttavia, è possibile eseguire la migrazione di un pool di chat di gruppo di Lync&nbsp;2010 o di Office Communications Server 2007 R2 a un singolo pool di server di chat persistente di lync Server 2013. È possibile aggiungere ulteriori nuovi pool di server Chat persistente nella distribuzione per soddisfare i requisiti normativi, ad esempio per mantenere i dati all'interno di una determinata geografia.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

