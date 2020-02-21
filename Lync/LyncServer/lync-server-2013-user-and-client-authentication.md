---
title: 'Lync Server 2013: autenticazione utente e client'
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
ms.openlocfilehash: 4dbddb0dab36a8ad805691196a00a3dc8bf6f9d6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-and-client-authentication-for-lync-server-2013"></a><span data-ttu-id="640fb-102">Autenticazione utente e client per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="640fb-102">User and client authentication for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="640fb-103">_**Ultimo argomento modificato:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="640fb-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="640fb-104">Un utente attendibile è quello le cui credenziali sono state autenticate da un server attendibile in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="640fb-104">A trusted user is one whose credentials have been authenticated by a trusted server in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="640fb-105">Tale server è in genere un server Standard Edition, Enterprise Edition Front End o Director.</span><span class="sxs-lookup"><span data-stu-id="640fb-105">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="640fb-106">Lync Server 2013 si basa su servizi di dominio Active Directory come singolo archivio back-end attendibile delle credenziali utente.</span><span class="sxs-lookup"><span data-stu-id="640fb-106">Lync Server 2013 relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>

<span data-ttu-id="640fb-107">Per autenticazione si intende la fornitura delle credenziali utente a un server trusted.</span><span class="sxs-lookup"><span data-stu-id="640fb-107">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="640fb-108">Lync Server 2013 utilizza i seguenti protocolli di autenticazione, a seconda dello stato e della posizione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="640fb-108">Lync Server 2013 uses the following authentication protocols, depending on the status and location of the user.</span></span>

  - <span data-ttu-id="640fb-p103">**Protocollo di sicurezza MIT Kerberos versione 5** per gli utenti interni con credenziali di Active Directory. Kerberos richiede la connettività client a Servizi di dominio Active Directory, pertanto non può essere utilizzato per l'autenticazione di client esterni al firewall aziendale.</span><span class="sxs-lookup"><span data-stu-id="640fb-p103">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials. Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>

  - <span data-ttu-id="640fb-p104">**Protocollo NTLM** per gli utenti con credenziali di Active Directory che si connettono da un endpoint esterno al firewall aziendale. Il servizio Access Edge passa le richieste di accesso a un Director, se presente, o a un Front End Server per l'autenticazione. Il servizio Access Edge in sé non esegue alcuna autenticazione.</span><span class="sxs-lookup"><span data-stu-id="640fb-p104">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall. The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication. The Access Edge service itself performs no authentication.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="640fb-114">Il protocollo NTLM offre una minore protezione dagli attacchi rispetto a Kerberos, pertanto viene utilizzato il meno possibile da alcune organizzazioni.</span><span class="sxs-lookup"><span data-stu-id="640fb-114">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="640fb-115">Di conseguenza, l'accesso a Lync Server 2013 potrebbe essere limitato all'interno o ai client connessi tramite una connessione VPN o DirectAccess.</span><span class="sxs-lookup"><span data-stu-id="640fb-115">As a result, access to Lync Server 2013 might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span>

    
    </div>

  - <span data-ttu-id="640fb-p106">**Protocollo digest** per i cosiddetti utenti anonimi. Gli utenti anonimi sono utenti esterni che non dispongono di credenziali di Active Directory riconosciute, ma che sono stati invitati a una conferenza locale e sono in possesso di una chiave di conferenza valida. L'autenticazione del digest non viene utilizzata per altre interazioni client.</span><span class="sxs-lookup"><span data-stu-id="640fb-p106">**Digest protocol** for so-called anonymous users. Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key. Digest authentication is not used for other client interactions.</span></span>

<span data-ttu-id="640fb-119">L'autenticazione di Lync Server 2013 è costituita da due fasi:</span><span class="sxs-lookup"><span data-stu-id="640fb-119">Lync Server 2013 authentication consists of two phases:</span></span>

1.  <span data-ttu-id="640fb-120">Viene stabilita un'associazione di sicurezza tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="640fb-120">A security association is established between the client and the server.</span></span>

2.  <span data-ttu-id="640fb-p107">Il client e il server utilizzano l'associazione di sicurezza esistente per firmare i messaggi inviati e per verificare i messaggi ricevuti. I messaggi non autenticati provenienti da un client non vengono accettati quando viene abilitata l'autenticazione nel server.</span><span class="sxs-lookup"><span data-stu-id="640fb-p107">The client and server use the existing security association to sign messages that they send and to verify the messages they receive. Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>

<span data-ttu-id="640fb-p108">L'attendibilità utente è associata a ogni messaggio originato da un utente e non all'identità dell'utente. Il server verifica in ogni messaggio la validità delle credenziali utente. Se le credenziali utente sono valide, il messaggio non riceve richieste di autenticazione non solo dal primo server che lo riceve, ma anche da tutti gli altri server del cloud di server trusted.</span><span class="sxs-lookup"><span data-stu-id="640fb-p108">User trust is attached to each message that originates from a user, not to the user identity itself. The server checks each message for valid user credentials. If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>

<span data-ttu-id="640fb-126">Gli utenti con credenziali valide emesse da un partner federato sono attendibili, ma è possibile che a causa di vincoli aggiuntivi non sia loro consentito di usufruire di tutti i privilegi accordati agli utenti interni.</span><span class="sxs-lookup"><span data-stu-id="640fb-126">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>

<span data-ttu-id="640fb-127">I protocolli ICE e TURN utilizzano inoltre la richiesta di autenticazione del digest come descritto nella specifica RFC TURN IETF.</span><span class="sxs-lookup"><span data-stu-id="640fb-127">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>

<span data-ttu-id="640fb-128">I certificati client forniscono un modo alternativo per l'autenticazione degli utenti da parte di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="640fb-128">Client certificates provide an alternate way for users to be authenticated by Lync Server 2013.</span></span> <span data-ttu-id="640fb-129">Invece di fornire un nome utente e una password, gli utenti dispongono di un certificato e della chiave privata corrispondente al certificato necessario per risolvere una richiesta di verifica crittografica.</span><span class="sxs-lookup"><span data-stu-id="640fb-129">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="640fb-130">(Il certificato deve avere un nome soggetto o un nome alternativo del soggetto che identifica l'utente e deve essere emesso da una CA radice attendibile per i server che eseguono Lync Server 2013, entro il periodo di validità del certificato e non è stato revocato). Per essere autenticati, gli utenti devono solo digitare un PIN (Personal Identification Number).</span><span class="sxs-lookup"><span data-stu-id="640fb-130">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Lync Server 2013, be within the certificate’s validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="640fb-131">I certificati sono particolarmente utili per i telefoni e altri dispositivi che eseguono Microsoft Lync 2013 Phone Edition in cui è difficile immettere un nome utente e/o una password.</span><span class="sxs-lookup"><span data-stu-id="640fb-131">Certificates are particularly useful for telephones and other devices running Microsoft Lync 2013 Phone Edition where it is difficult to enter a user name and/or password.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

