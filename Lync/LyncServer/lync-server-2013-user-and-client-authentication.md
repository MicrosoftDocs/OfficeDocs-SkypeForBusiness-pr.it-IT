---
title: 'Lync Server 2013: autenticazione utente e client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User and client authentication for Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59893868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 052c65bad805dff0d993cbf8533593c1f12915a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-and-client-authentication-for-lync-server-2013"></a>Autenticazione utente e client per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-11_

Un utente attendibile è colui le cui credenziali sono state autenticate da un server attendibile in Microsoft Lync Server 2013. Questo server è in genere un server Standard Edition, un server front-end Enterprise Edition o un Director. Lync Server 2013 si basa su servizi di dominio Active Directory come singolo repository back-end attendibile delle credenziali utente.

L'autenticazione è la fornitura di credenziali utente a un server attendibile. Lync Server 2013 USA i protocolli di autenticazione seguenti, a seconda dello stato e della posizione dell'utente.

  - **Protocollo di sicurezza Kerberos versione 5 mit** per gli utenti interni con credenziali di Active Directory. Kerberos richiede la connettività client ai servizi di dominio Active Directory, motivo per cui non può essere usato per l'autenticazione dei client esterni al firewall aziendale.

  - **Protocollo NTLM** per gli utenti con le credenziali di Active Directory che si connettono da un endpoint esterno al firewall aziendale. Il servizio Access Edge passa le richieste di accesso a un amministratore, se presente, o a un server front-end per l'autenticazione. Il servizio Access Edge non esegue alcuna autenticazione.
    
    <div>
    

    > [!NOTE]  
    > Il protocollo NTLM offre una protezione dagli attacchi più debole rispetto a Kerberos, in modo che alcune organizzazioni riducano l'uso di NTLM. Di conseguenza, l'accesso a Lync Server 2013 potrebbe essere limitato a utenti interni o client connessi tramite una connessione VPN o DirectAccess.

    
    </div>

  - **Protocollo digest** per i cosiddetti utenti anonimi. Gli utenti anonimi sono utenti esterni che non hanno credenziali Active Directory riconosciute, ma che sono stati invitati a una conferenza locale e possiedono una chiave di conferenza valida. L'autenticazione digest non viene utilizzata per altre interazioni client.

L'autenticazione di Lync Server 2013 è costituita da due fasi:

1.  Viene stabilita un'associazione di protezione tra il client e il server.

2.  Il client e il server utilizzano l'associazione di protezione esistente per firmare i messaggi inviati e per verificare i messaggi ricevuti. I messaggi non autenticati da un client non vengono accettati quando l'autenticazione è abilitata sul server.

L'attendibilità dell'utente è associata a ciascun messaggio che proviene da un utente, non all'identità dell'utente stesso. Il server verifica che ogni messaggio abbia credenziali utente valide. Se le credenziali utente sono valide, il messaggio non viene contestato solo dal primo server per riceverlo, ma da tutti gli altri server nel cloud del server trusted.

Gli utenti con credenziali valide emesse da un partner federato sono attendibili ma opzionalmente limitati da vincoli aggiuntivi per cui non possono usufruire dell'intera gamma di privilegi concessi agli utenti interni.

I protocolli ICE e TURN usano anche la sfida digest come descritto in IETF TURN RFC.

I certificati client rappresentano un modo alternativo per consentire agli utenti di essere autenticati da Lync Server 2013. Anziché fornire un nome utente e una password, gli utenti hanno un certificato e la chiave privata corrispondente al certificato necessario per risolvere un'autenticazione crittografica. Questo certificato deve avere un nome soggetto o un nome alternativo soggetto che identifichi l'utente e che deve essere emesso da una CA radice attendibile per i server che hanno eseguito Lync Server 2013, che si trova nel periodo di validità del certificato e non è stato revocato. Per essere autenticati, gli utenti devono digitare solo un PIN (Personal Identification Number). I certificati sono particolarmente utili per i telefoni e altri dispositivi che usano Microsoft Lync 2013 Phone Edition in cui è difficile immettere un nome utente e/o una password.

</div>

<span> </span>

</div>

</div>

</div>

