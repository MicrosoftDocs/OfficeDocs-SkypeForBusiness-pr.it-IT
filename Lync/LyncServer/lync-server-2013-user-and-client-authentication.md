---
title: 'Lync Server 2013: autenticazione utente e client'
description: 'Lync Server 2013: autenticazione utente e client.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User and client authentication for Lync Server 2013
ms:assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481132(v=OCS.15)
ms:contentKeyID: 59893868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef545dda38e9ab4236e93df769ead393648194cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569812"
---
# <a name="user-and-client-authentication-for-lync-server-2013"></a>Autenticazione utente e client per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-11_

Un utente attendibile è quello le cui credenziali sono state autenticate da un server attendibile in Microsoft Lync Server 2013. Tale server è in genere un server Standard Edition, Enterprise Edition Front End o Director. Lync Server 2013 si basa su servizi di dominio Active Directory come singolo archivio back-end attendibile delle credenziali utente.

Per autenticazione si intende la fornitura delle credenziali utente a un server trusted. Lync Server 2013 utilizza i seguenti protocolli di autenticazione, a seconda dello stato e della posizione dell'utente.

  - **Protocollo di sicurezza MIT Kerberos versione 5** per gli utenti interni con credenziali di Active Directory. Kerberos richiede la connettività client a Servizi di dominio Active Directory, pertanto non può essere utilizzato per l'autenticazione di client esterni al firewall aziendale.

  - **Protocollo NTLM** per gli utenti con credenziali di Active Directory che si connettono da un endpoint esterno al firewall aziendale. Il servizio Access Edge passa le richieste di accesso a un Director, se presente, o a un Front End Server per l'autenticazione. Il servizio Access Edge in sé non esegue alcuna autenticazione.
    
    <div>
    

    > [!NOTE]  
    > Il protocollo NTLM offre una minore protezione dagli attacchi rispetto a Kerberos, pertanto viene utilizzato il meno possibile da alcune organizzazioni. Di conseguenza, l'accesso a Lync Server 2013 potrebbe essere limitato all'interno o ai client connessi tramite una connessione VPN o DirectAccess.

    
    </div>

  - **Protocollo digest** per i cosiddetti utenti anonimi. Gli utenti anonimi sono utenti esterni che non dispongono di credenziali di Active Directory riconosciute, ma che sono stati invitati a una conferenza locale e sono in possesso di una chiave di conferenza valida. L'autenticazione del digest non viene utilizzata per altre interazioni client.

L'autenticazione di Lync Server 2013 è costituita da due fasi:

1.  Viene stabilita un'associazione di sicurezza tra il client e il server.

2.  Il client e il server utilizzano l'associazione di sicurezza esistente per firmare i messaggi inviati e per verificare i messaggi ricevuti. I messaggi non autenticati provenienti da un client non vengono accettati quando viene abilitata l'autenticazione nel server.

L'attendibilità utente è associata a ogni messaggio originato da un utente e non all'identità dell'utente. Il server verifica in ogni messaggio la validità delle credenziali utente. Se le credenziali utente sono valide, il messaggio non riceve richieste di autenticazione non solo dal primo server che lo riceve, ma anche da tutti gli altri server del cloud di server trusted.

Gli utenti con credenziali valide emesse da un partner federato sono attendibili, ma è possibile che a causa di vincoli aggiuntivi non sia loro consentito di usufruire di tutti i privilegi accordati agli utenti interni.

I protocolli ICE e TURN utilizzano inoltre la richiesta di autenticazione del digest come descritto nella specifica RFC TURN IETF.

I certificati client forniscono un modo alternativo per l'autenticazione degli utenti da parte di Lync Server 2013. Invece di fornire un nome utente e una password, gli utenti dispongono di un certificato e della chiave privata corrispondente al certificato necessario per risolvere una richiesta di verifica crittografica. (Il certificato deve avere un nome soggetto o un nome alternativo del soggetto che identifica l'utente e deve essere emesso da una CA radice attendibile per i server che eseguono Lync Server 2013, entro il periodo di validità del certificato e non è stato revocato). Per essere autenticati, gli utenti devono solo digitare un PIN (Personal Identification Number). I certificati sono particolarmente utili per i telefoni e altri dispositivi che eseguono Microsoft Lync 2013 Phone Edition in cui è difficile immettere un nome utente e/o una password.

</div>

<span> </span>

</div>

</div>

</div>

