---
title: Eseguire la compatibilità con le versioni precedenti del server Chat persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 329415e7bae43bbbfd3a77da39e99049f4fe617e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a>Eseguire la compatibilità con le versioni precedenti del server Chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

Lync Server 2013, endpoint del server Chat persistente, consente di creare un URL semplice che punta a un pool di server Chat persistente. Questa operazione è utile per i client legacy (Microsoft Office Communications Server 2007 R2 Group Chat Server o Lync Server 2010, Group Chat) perché gli utenti possono immettere un URL semplice nella configurazione manuale quando si tenta di puntare il client legacy a un computer che esegue Lync 2013, Chat persistente. Questo endpoint non viene utilizzato da Chat persistente ed è necessario solo per i client legacy. Questa operazione è utile per il periodo interinale in cui è possibile eseguire la migrazione delle sale, ma i client di Lync 2013 non sono stati distribuiti nell'intera organizzazione. Gli utenti che eseguono Lync 2010 Group Chat (client) possono comunque connettersi al server back-end del server di chat persistente.

Non è necessario creare più endpoint del server Chat persistente. serve solo una per ogni pool di server Chat persistente. Gli amministratori possono creare più endpoint (uno per pool), ma i client legacy possono essere configurati per la connessione a un solo pool alla volta. Nello scenario usuale o mainstream, la distribuzione legacy è solo un pool. Una nuova distribuzione generalmente esegue la migrazione del pool a un nuovo Lync Server 2013 e potrebbe aggiungere alcuni nuovi pool di server Chat persistente aggiuntivi.

Uno scenario di questo tipo in genere segue questo schema:

  - È possibile amministrare gli utenti con un solo Lync Server 2010, un pool di chat di gruppo e i client di chat di gruppo di Lync 2010 che si connettono al pool utilizzando\<un utente\>noto (SIP predefinito: OCSChat@ domainname. com o uno simile). Gli utenti sono servizi di dominio Active Directory abilitati per SIP e il servizio di ricerca esegue la registrazione per ricevere le richieste in arrivo.

  - Successivamente, si installa un server di chat persistente di Lync Server 2013 e un pool di server Chat persistente.

  - In un momento in cui gli utenti sono in genere offline, ad esempio durante il weekend:
    
      - Disattivare Lync Server 2010, Group Chat.
    
      - Eseguire la migrazione dei dati dal pool di chat di gruppo di Lync Server 2010 al pool di server Chat persistente di Lync Server 2013.
    
      - Eliminare l'utente noto da servizi di dominio Active Directory.
    
      - Creare un nuovo *endpoint legacy* con lo stesso URI SIP dell'utente noto eliminato in precedenza.
    
      - Avviare Lync Server 2013, server Chat persistente.

  - Gli utenti eseguono l'accesso utilizzando la propria chat di gruppo di Lync 2010 (client) e si connettono ai dati senza dover modificare alcuna configurazione.

  - In un secondo momento, è possibile rimuovere le autorizzazioni di Lync Server 2010, Group Chat. Successivamente, è possibile distribuire Lync Server 2013, il server Chat persistente e installare nuovi pool di server Chat persistente di Lync Server 2013.

Per informazioni dettagliate sulla migrazione da Lync Server 2010, Group Chat a Lync Server 2013, server Chat persistente, vedere [migrazione da Lync server 2010, Group Chat o Office Communications server 2007 R2 Group Chat a Lync server 2013, server Chat persistente](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

Per eseguire la compatibilità con le versioni precedenti (per creare un endpoint del server Chat persistente che punta a un pool di server Chat persistente, che può essere utilizzato dai client del pool di chat di gruppo legacy):

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

Successivamente, configurare i client di chat persistente per utilizzare quell'indirizzo SIP come loro oggetto contatto. L'indirizzo SIP viene creato con il cmdlet **New-CsPersistentChatEndpoint** per un pool di server Chat persistente specifico.

Per aggiungere l'endpoint del server Chat persistente utilizzando l'interfaccia della riga di comando di Windows PowerShell, prendere in considerazione l'esempio seguente. In questo caso si configura l'oggetto contatto con il nome "persistentchat" nella topologia "contoso.com", dove il nome di dominio completo (FQDN) del pool è "pcpool.contoso.com":

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

