---
title: Processo di migrazione - Dettagli
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process - details
ms:assetid: ca7e352c-9bde-47d9-8273-5cf2fdfdfe7e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205264(v=OCS.15)
ms:contentKeyID: 48185412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39560d69842c104c7db956418dabac9aa6d29d7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980918"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process---details"></a>Processo di migrazione - Dettagli

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

Usare i prerequisiti seguenti e i passaggi dettagliati per eseguire la migrazione di Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat in Lync Server 2013, Persistent Chat Server.

<div>

## <a name="prerequisites-for-migration"></a>Prerequisiti per la migrazione

Verificare di avere soddisfatto i prerequisiti seguenti prima di eseguire la migrazione di Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat a Lync Server 2013, Persistent Chat Server.

1.  Distribuire almeno un pool di Lync Server 2013. Se si dispone di più pool di Lync Server 2013, decidere quale pool di Lync Server 2013 sarà il pool Home per il nuovo pool di server di chat persistente di Lync Server 2013.

2.  Installare il pool di server di chat persistente di Lync Server 2013. Sarà vuota (nessun categorie, sale o componenti aggiuntivi). Prima di eseguire la migrazione delle categorie, delle sale o dei componenti aggiuntivi legacy, è possibile creare sale, categorie o componenti aggiuntivi in Lync Server 2013, la distribuzione del server di chat persistente.
    
    <div>
    

    > [!IMPORTANT]  
    > Tieni presente che questi elementi appena creati potrebbero essere in conflitto con gli elementi legacy migrati. Evitare qualsiasi conflitto di denominazione; in caso contrario, verranno sovrascritti quando si esegue la migrazione dei dati legacy.

    
    </div>

</div>

<div>

## <a name="preparing-the-source-data-for-migration"></a>Preparazione dei dati di origine per la migrazione

Eseguire la procedura seguente per preparare correttamente i dati di origine per la migrazione.

1.  Eseguire il backup dei database di origine per Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat. Per informazioni dettagliate sul backup di SQL Server, vedere "Panoramica del backup (SQL Server)" <http://go.microsoft.com/fwlink/p/?linkid=254851>all'indirizzo.
    
    <div>
    

    > [!IMPORTANT]  
    > I servizi di dominio Active Directory dovrebbero essere gli stessi. Come condizione per la migrazione, non è possibile eseguire la migrazione a un pool in una distribuzione diversa (in particolare in una foresta di Active Directory diversa).

    
    </div>

2.  Esaminare le chat room e la configurazione delle categorie di Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat. Tutte le modifiche apportate alle categorie, alle sale o ai componenti aggiuntivi nella distribuzione legacy esistente verranno eseguite dallo strumento di amministrazione di Group Chat.
    
    <div>
    

    > [!TIP]  
    > Qualsiasi modifica apportata a categorie, sale o componenti aggiuntivi in Lync Server 2013, la distribuzione del server di chat persistente viene eseguita dal pannello di controllo di Lync Server o dai cmdlet di Windows PowerShell.

    
    </div>
    
    Seguire questa procedura per preparare il sistema legacy per la migrazione.
    
    1.  Il server di chat persistente supporta un singolo livello di categorie, a differenza di un set gerarchico profondo di categorie. Dopo la migrazione, le sottocategorie sono prefissate con i nomi di categoria padre completo. È consigliabile semplificare e appiattire la struttura delle categorie esistente in modo che la struttura risultante soddisfi le proprie esigenze.
    
    2.  Verificare i **responsabili** della categoria radice. Se sono presenti Manager di questo livello, questi utenti verranno aggiunti come **responsabili a tutte le sale** dopo la migrazione. Se non si tratta di un requisito per l'organizzazione, è necessario rimuovere questi Manager dalla categoria radice.
    
    3.  Verificare la lunghezza dei nomi delle chat room. Dopo la migrazione, a causa di strutture di categoria semplificate, se le sale sono presenti in una categoria figlio, sono preceduti da nomi di categoria padre completo. Il limite di denominazione è 256 caratteri, inclusi i nomi delle categorie padre. È necessario verificare la lunghezza dei nomi delle stanze e possibilmente accorciare la lunghezza, se troppo lunga.
    
    4.  In Lync Server 2013, se le impostazioni per gli **inviti** alle categorie sono impostate su true, è possibile scegliere vero o falso per gli inviti alle camere in tale categoria. Tuttavia, se le impostazioni per gli inviti alle categorie sono impostate su false, le sale in tale categoria hanno inviti disattivati. Prima di eseguire la migrazione, è necessario reimpostare le impostazioni dell'invito nella versione legacy di Group Chat Server di Lync Server, se si vuole che le camere siano presenti in una categoria specifica. In caso contrario, durante la migrazione, Lync Server 2013 Visualizza gli avvisi e imposta le camere sul valore predefinito false.
    
    5.  Se sono stati usati file nelle chat room, è necessario eseguire il XCOPY manuale dei file nel nuovo archivio di file della chat persistente dopo la migrazione. Gli strumenti non lo fanno.
    
    6.  Se si dispone di utenti e camere federati con utenti federati, tenere presente che il server di chat persistente non supporta la Federazione. Verranno migrate le camere con gli utenti federati; Tuttavia, gli utenti stessi non saranno in grado di accedere al contenuto, perché l'accesso federato non è supportato.
    
    7.  Identificare le sale di cui non si vuole eseguire la migrazione e contrassegnarle come disabilitate.
    
    8.  Identificare la data oltre la quale si vuole eseguire la migrazione del contenuto della chat room. Ad esempio, potresti non voler eseguire la migrazione dei messaggi prima del 1 ° gennaio 2010, perché questi messaggi potrebbero essere obsoleti o non rilevanti per la migrazione.

</div>

<div>

## <a name="performing-the-migration"></a>Esecuzione della migrazione

Eseguire la procedura seguente per eseguire la migrazione del server di chat di gruppo legacy.

1.  Arrestare Lync Server 2010, Group Chat, Office Communications Server 2007 R2 Group Chat o Lync Server 2013, servizi di chat server permanenti. Tutti i servizi devono essere interrotti, quindi pianificare questa operazione in un momento in cui si verificano tempi di inattività sufficienti. Come descritto in precedenza, assicurati di eseguire il backup del database corrente della chat di gruppo.

2.  Eseguire il cmdlet **Export-CsPersistentChatData** di Windows PowerShell come membro del ruolo di amministratore RBAC della chat persistente (CsPersistentChatAdministrator). Per informazioni dettagliate sui cmdlet di esportazione/importazione, vedere [risoluzione dei problemi relativi alla configurazione del server di chat persistente con i cmdlet di Windows PowerShell in Lync server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).
    
    Esaminare il contenuto esportato.

3.  Prima di essere pronti per l'importazione, arrestare Lync Server 2013, servizi server di chat persistente. Tutti i servizi devono essere interrotti, quindi pianificare questa operazione in un momento in cui si verificano tempi di inattività sufficienti.

4.  Eseguire una copia di backup del database della chat persistente se sono state create categorie, sale o componenti aggiuntivi nella distribuzione di Lync Server 2013 prima della migrazione. Il processo di esportazione/importazione sarà in grado di unire i dati legacy alla distribuzione di Lync Server 2013, ma si vorrà eseguire il backup del database nel caso in cui il contenuto venga sovrascritto in modo involontario, ad esempio se esistono ancora conflitti di denominazione.

5.  Eseguire il cmdlet **Import-CsPersistentChatData** di Windows PowerShell (strumento di importazione), con un comando **whatIf** per popolare il server back-end del pool del server di chat persistente con i dati migrati. Alcune conversioni si verificano nel processo per adattare il modello di amministrazione semplificato. Correggere eventuali errori o avvisi visualizzati.

6.  Eseguire il cmdlet **Import-CsPersistentChatData** di Windows PowerShell per il server di chat persistente come membro del ruolo di amministratore RBAC della chat persistente (CsPersistentChatAdministrator). Per informazioni dettagliate sui cmdlet di esportazione/importazione, vedere [risoluzione dei problemi relativi alla configurazione del server di chat persistente con i cmdlet di Windows PowerShell in Lync server 2013](lync-server-2013-troubleshooting-persistent-chat-server-configuration-using-windows-powershell-cmdlets.md).

7.  È necessario XCOPY tutti i file caricati (l'intera cartella) nel nuovo Lync Server 2013, l'archivio di file della chat persistente.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync 2013 (client) non supporta il caricamento o la visualizzazione di file nelle chat room. È comunque possibile usare il client legacy per pubblicare e visualizzare i file nella sala.

    
    </div>

8.  Porta l'URI Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat Server Lookup a Lync Server 2013, l'oggetto contatto del server di chat persistente. I passaggi seguenti sono obbligatori se la chat di gruppo di Lync 2010 o i client di chat di gruppo di Office Communicator 2007 R2 devono connettersi alla versione più recente di Lync 2013, la chat persistente (client) dopo la migrazione senza alcuna modifica della configurazione lato client:
    
      - Eliminare l'account\<utente del\>Server di ricerca di OCSChat@ NomeDominio. com. Questa operazione è stata usata per posizionare il puntatore del servizio di ricerca in Lync Server 2010, chat di gruppo. È possibile disinstallare il pool e rimuovere le voci attendibili in un secondo momento.
    
      - Crea un endpoint legacy (oggetto Contact del server di chat persistente) eseguendo il cmdlet di Windows PowerShell, **New-CsPersistentChatEndpoint**, con l'URI SIP identico in modo che il client legacy funzioni efficacemente quando il servizio viene riavviato.
    
    Il processo di migrazione obbligatoria è completato a questo punto. Lync 2010 Group Chat (client) o Office Communicator 2007 R2 Group Chat (client) può connettersi al nuovo pool di server di chat persistente ora, in modo trasparente.
    
    Seguire queste procedure aggiuntive per la disattivazione per Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat.

9.  Avviare i servizi del server di chat persistente attivando tutti i computer nel nuovo pool del server di chat persistente.

10. Utilizzare il pannello di controllo di Lync Server e i cmdlet di Windows PowerShell per verificare che i dati siano stati correttamente migrati.

11. Disinstallare Lync 2010 Group Chat o Office Communicator 2007 R2 Group Chat dai computer del pool di Group Chat Server.

12. Eliminare l'applicazione attendibile e il pool di applicazioni attendibili usando i cmdlet di Windows PowerShell. Questo elimina questi elementi dall'Central Management store e dalle voci di servizio attendibili associate (TSE) da Active Directory. In alternativa, questo passaggio funziona usando il generatore di topologie (anche le applicazioni/i pool attendibili hanno un nodo dedicato).

13. Ora puoi iniziare a abilitare la funzionalità del server di chat persistente tramite i nuovi client. Per informazioni dettagliate sull'abilitazione del server di chat persistente, vedere [distribuzione di un server di chat persistente in Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md).
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 supporta più pool di server di chat persistenti. Tuttavia, sosteniamo la migrazione di una chat di gruppo di Lync 2010 o di&nbsp;un pool di chat di Office Communications Server 2007 R2 a un singolo pool di server di chat di lync Server 2013. È possibile aggiungere altri nuovi pool di server di chat persistenti nella distribuzione per soddisfare le esigenze di regolamentazione, ad esempio per mantenere i dati all'interno di una data geografia.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

