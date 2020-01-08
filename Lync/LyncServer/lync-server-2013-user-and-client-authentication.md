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

# <a name="user-and-client-authentication-for-lync-server-2013"></a><span data-ttu-id="25e23-102">Autenticazione utente e client per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25e23-102">User and client authentication for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25e23-103">_**Argomento Ultima modifica:** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="25e23-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="25e23-104">Un utente attendibile è colui le cui credenziali sono state autenticate da un server attendibile in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25e23-104">A trusted user is one whose credentials have been authenticated by a trusted server in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="25e23-105">Questo server è in genere un server Standard Edition, un server front-end Enterprise Edition o un Director.</span><span class="sxs-lookup"><span data-stu-id="25e23-105">This server is usually a Standard Edition server, Enterprise Edition Front End Server, or Director.</span></span> <span data-ttu-id="25e23-106">Lync Server 2013 si basa su servizi di dominio Active Directory come singolo repository back-end attendibile delle credenziali utente.</span><span class="sxs-lookup"><span data-stu-id="25e23-106">Lync Server 2013 relies on Active Directory Domain Services as the single, trusted back-end repository of user credentials.</span></span>

<span data-ttu-id="25e23-107">L'autenticazione è la fornitura di credenziali utente a un server attendibile.</span><span class="sxs-lookup"><span data-stu-id="25e23-107">Authentication is the provision of user credentials to a trusted server.</span></span> <span data-ttu-id="25e23-108">Lync Server 2013 USA i protocolli di autenticazione seguenti, a seconda dello stato e della posizione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="25e23-108">Lync Server 2013 uses the following authentication protocols, depending on the status and location of the user.</span></span>

  - <span data-ttu-id="25e23-109">**Protocollo di sicurezza Kerberos versione 5 mit** per gli utenti interni con credenziali di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="25e23-109">**MIT Kerberos version 5 security protocol** for internal users with Active Directory credentials.</span></span> <span data-ttu-id="25e23-110">Kerberos richiede la connettività client ai servizi di dominio Active Directory, motivo per cui non può essere usato per l'autenticazione dei client esterni al firewall aziendale.</span><span class="sxs-lookup"><span data-stu-id="25e23-110">Kerberos requires client connectivity to Active Directory Domain Services, which is why it cannot be used for authenticating clients outside the corporate firewall.</span></span>

  - <span data-ttu-id="25e23-111">**Protocollo NTLM** per gli utenti con le credenziali di Active Directory che si connettono da un endpoint esterno al firewall aziendale.</span><span class="sxs-lookup"><span data-stu-id="25e23-111">**NTLM protocol** for users with Active Directory credentials who are connecting from an endpoint outside the corporate firewall.</span></span> <span data-ttu-id="25e23-112">Il servizio Access Edge passa le richieste di accesso a un amministratore, se presente, o a un server front-end per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="25e23-112">The Access Edge service passes logon requests to a Director, if present, or a Front End Server for authentication.</span></span> <span data-ttu-id="25e23-113">Il servizio Access Edge non esegue alcuna autenticazione.</span><span class="sxs-lookup"><span data-stu-id="25e23-113">The Access Edge service itself performs no authentication.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="25e23-114">Il protocollo NTLM offre una protezione dagli attacchi più debole rispetto a Kerberos, in modo che alcune organizzazioni riducano l'uso di NTLM.</span><span class="sxs-lookup"><span data-stu-id="25e23-114">NTLM protocol offers weaker attack protection than Kerberos, so some organizations minimize usage of NTLM.</span></span> <span data-ttu-id="25e23-115">Di conseguenza, l'accesso a Lync Server 2013 potrebbe essere limitato a utenti interni o client connessi tramite una connessione VPN o DirectAccess.</span><span class="sxs-lookup"><span data-stu-id="25e23-115">As a result, access to Lync Server 2013 might be restricted to internal or clients connected through a VPN or DirectAccess connection.</span></span>

    
    </div>

  - <span data-ttu-id="25e23-116">**Protocollo digest** per i cosiddetti utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="25e23-116">**Digest protocol** for so-called anonymous users.</span></span> <span data-ttu-id="25e23-117">Gli utenti anonimi sono utenti esterni che non hanno credenziali Active Directory riconosciute, ma che sono stati invitati a una conferenza locale e possiedono una chiave di conferenza valida.</span><span class="sxs-lookup"><span data-stu-id="25e23-117">Anonymous users are outside users who do not have recognized Active Directory credentials but who have been invited to an on-premises conference and possess a valid conference key.</span></span> <span data-ttu-id="25e23-118">L'autenticazione digest non viene utilizzata per altre interazioni client.</span><span class="sxs-lookup"><span data-stu-id="25e23-118">Digest authentication is not used for other client interactions.</span></span>

<span data-ttu-id="25e23-119">L'autenticazione di Lync Server 2013 è costituita da due fasi:</span><span class="sxs-lookup"><span data-stu-id="25e23-119">Lync Server 2013 authentication consists of two phases:</span></span>

1.  <span data-ttu-id="25e23-120">Viene stabilita un'associazione di protezione tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="25e23-120">A security association is established between the client and the server.</span></span>

2.  <span data-ttu-id="25e23-121">Il client e il server utilizzano l'associazione di protezione esistente per firmare i messaggi inviati e per verificare i messaggi ricevuti.</span><span class="sxs-lookup"><span data-stu-id="25e23-121">The client and server use the existing security association to sign messages that they send and to verify the messages they receive.</span></span> <span data-ttu-id="25e23-122">I messaggi non autenticati da un client non vengono accettati quando l'autenticazione è abilitata sul server.</span><span class="sxs-lookup"><span data-stu-id="25e23-122">Unauthenticated messages from a client are not accepted when authentication is enabled on the server.</span></span>

<span data-ttu-id="25e23-123">L'attendibilità dell'utente è associata a ciascun messaggio che proviene da un utente, non all'identità dell'utente stesso.</span><span class="sxs-lookup"><span data-stu-id="25e23-123">User trust is attached to each message that originates from a user, not to the user identity itself.</span></span> <span data-ttu-id="25e23-124">Il server verifica che ogni messaggio abbia credenziali utente valide.</span><span class="sxs-lookup"><span data-stu-id="25e23-124">The server checks each message for valid user credentials.</span></span> <span data-ttu-id="25e23-125">Se le credenziali utente sono valide, il messaggio non viene contestato solo dal primo server per riceverlo, ma da tutti gli altri server nel cloud del server trusted.</span><span class="sxs-lookup"><span data-stu-id="25e23-125">If the user credentials are valid, the message is unchallenged not only by the first server to receive it but by all other servers in the trusted server cloud.</span></span>

<span data-ttu-id="25e23-126">Gli utenti con credenziali valide emesse da un partner federato sono attendibili ma opzionalmente limitati da vincoli aggiuntivi per cui non possono usufruire dell'intera gamma di privilegi concessi agli utenti interni.</span><span class="sxs-lookup"><span data-stu-id="25e23-126">Users with valid credentials issued by a federated partner are trusted but optionally prevented by additional constraints from enjoying the full range of privileges accorded to internal users.</span></span>

<span data-ttu-id="25e23-127">I protocolli ICE e TURN usano anche la sfida digest come descritto in IETF TURN RFC.</span><span class="sxs-lookup"><span data-stu-id="25e23-127">The ICE and TURN protocols also use the Digest challenge as described in the IETF TURN RFC.</span></span>

<span data-ttu-id="25e23-128">I certificati client rappresentano un modo alternativo per consentire agli utenti di essere autenticati da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="25e23-128">Client certificates provide an alternate way for users to be authenticated by Lync Server 2013.</span></span> <span data-ttu-id="25e23-129">Anziché fornire un nome utente e una password, gli utenti hanno un certificato e la chiave privata corrispondente al certificato necessario per risolvere un'autenticazione crittografica.</span><span class="sxs-lookup"><span data-stu-id="25e23-129">Instead of providing a user name and password, users have a certificate and the private key corresponding to the certificate that is required to resolve a cryptographic challenge.</span></span> <span data-ttu-id="25e23-130">Questo certificato deve avere un nome soggetto o un nome alternativo soggetto che identifichi l'utente e che deve essere emesso da una CA radice attendibile per i server che hanno eseguito Lync Server 2013, che si trova nel periodo di validità del certificato e non è stato revocato. Per essere autenticati, gli utenti devono digitare solo un PIN (Personal Identification Number).</span><span class="sxs-lookup"><span data-stu-id="25e23-130">(This certificate must have a subject name or subject alternative name that identifies the user and must be issued by a Root CA that is trusted by servers running Lync Server 2013, be within the certificate’s validity period, and not have been revoked.) To be authenticated, users only need to type in a personal identification number (PIN).</span></span> <span data-ttu-id="25e23-131">I certificati sono particolarmente utili per i telefoni e altri dispositivi che usano Microsoft Lync 2013 Phone Edition in cui è difficile immettere un nome utente e/o una password.</span><span class="sxs-lookup"><span data-stu-id="25e23-131">Certificates are particularly useful for telephones and other devices running Microsoft Lync 2013 Phone Edition where it is difficult to enter a user name and/or password.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

