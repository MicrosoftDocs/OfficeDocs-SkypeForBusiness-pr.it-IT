---
title: Eseguire la compatibilità con le versioni precedenti per il server Chat persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b512d18449c881efd856674477a727cec137b64c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a>Eseguire la compatibilità con le versioni precedenti per il server Chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

L'endpoint del server di chat persistente di Lync Server 2013 offre un modo per creare un URL semplice che punta a un pool di server di chat persistente. Questa funzionalità è utile per i client legacy (Microsoft Office Communications Server 2007 R2 Group Chat Server o Lync Server 2010, Group Chat) perché gli utenti possono immettere un URL semplice nella configurazione manuale quando si prova a puntare il client legacy a un computer che gestisce Lync 2013. Chat persistente. Questo endpoint non viene usato dalla chat persistente ed è obbligatorio solo per i client legacy. Questa operazione è utile per il periodo di interim in cui è possibile eseguire la migrazione delle sale, ma i client di Lync 2013 non sono stati distribuiti in tutta l'organizzazione. Gli utenti che hanno eseguito Lync 2010 Group Chat (client) possono comunque connettersi al server back-end del server di chat persistente.

Non è necessario creare più endpoint del server della chat persistente; è sufficiente una per ogni pool di server di chat persistente. Gli amministratori possono creare più endpoint (uno per ogni pool), ma i client legacy possono essere configurati per la connessione a un solo pool alla volta. Nello scenario usuale o mainstream, la distribuzione legacy è un solo pool. Una nuova distribuzione in genere esegue la migrazione del pool a un nuovo Lync Server 2013 e può aggiungere alcuni nuovi pool di server di chat persistente aggiuntivi.

Questo scenario mainstream segue in genere questo modello:

  - Si amministrano gli utenti con un solo Lync Server 2010, un pool di chat di gruppo e i client di chat di gruppo di Lync 2010 si connettono a tale pool usando un\<utente noto\>(SIP predefinito: OCSChat@ NomeDominio. com o uno simile). Gli utenti sono servizi di dominio Active Directory abilitati per SIP e il servizio di ricerca viene registrato con loro per ricevere le richieste in arrivo.

  - In seguito si installerà un server di chat persistente di Lync Server 2013 e un pool di server di chat persistente.

  - Durante un periodo in cui gli utenti sono in genere offline, ad esempio un week-end:
    
      - Disattivare Lync Server 2010, chat di gruppo.
    
      - Eseguire la migrazione dei dati da Lync Server 2010, pool di chat di gruppo al pool di server di chat persistente di Lync Server 2013.
    
      - Eliminare l'utente noto da servizi di dominio Active Directory.
    
      - Crea un nuovo *endpoint legacy* con lo stesso URI SIP dell'utente ben noto in precedenza eliminato.
    
      - Avviare Lync Server 2013, server di chat permanenti.

  - Gli utenti accedono di nuovo usando la chat di gruppo di Lync 2010 (client) e si connettono ai dati senza dover modificare alcuna configurazione.

  - In un secondo momento, è possibile rimuovere la Commissione di Lync Server 2010, chat di gruppo. In seguito, è possibile distribuire Lync Server 2013, Persistent Chat Server e installare nuovi pool di server di chat persistenti di Lync Server 2013.

Per informazioni dettagliate sulla migrazione da Lync Server 2010, chat di gruppo a Lync Server 2013, server di chat persistente, vedere [migrazione da Lync server 2010, chat di gruppo o Office Communications server 2007 R2 Chat di gruppo in Lync server 2013, server di chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

Per eseguire la compatibilità con le versioni precedenti (per creare un endpoint del server di chat persistente che punta a un pool di server di chat persistente, che può essere usato dai client del pool di chat di gruppo legacy):

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

Configurare quindi i client di chat permanenti per usare l'indirizzo SIP come oggetto contatto. L'indirizzo SIP viene creato con il cmdlet **New-CsPersistentChatEndpoint** per un pool di server di chat persistente specifico.

Per aggiungere l'endpoint del server di chat persistente usando l'interfaccia della riga di comando di Windows PowerShell, prendere in considerazione l'esempio seguente. In questo caso, devi configurare l'oggetto contatto per essere denominato "persistentchat" nella topologia "contoso.com", in cui il nome di dominio completo del pool è "pcpool.contoso.com":

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a>Vedere anche


[Migrazione da Lync Server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat al server chat persistente di Lync Server 2013](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

