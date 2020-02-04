---
title: 'Lync Server 2013: istruzioni per la configurazione speciale per le transazioni sintetiche'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a15177a3c4548b235bf01a10274168e4a830fad3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="e0f77-102">Istruzioni per la configurazione speciale per le transazioni sintetiche in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e0f77-102">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0f77-103">_**Argomento Ultima modifica:** 2015-11-16_</span><span class="sxs-lookup"><span data-stu-id="e0f77-103">_**Topic Last Modified:** 2015-11-16_</span></span>

<span data-ttu-id="e0f77-104">La maggior parte delle transazioni sintetiche può essere eseguita in un nodo Watcher così com'è; ovvero, non appena la transazione sintetica è stata aggiunta alle impostazioni di configurazione del nodo Watcher, il nodo Watcher può iniziare a usare la transazione sintetica durante le sessioni di test.</span><span class="sxs-lookup"><span data-stu-id="e0f77-104">Most synthetic transactions can run on a watcher node as-is; that is, as soon as the synthetic transaction has been added to the watcher node configuration settings, the watcher node can begin using the synthetic transaction during its test passes.</span></span> <span data-ttu-id="e0f77-105">Tuttavia, questo non è vero per tutte le transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="e0f77-105">However, this is not true for all synthetic transactions.</span></span> <span data-ttu-id="e0f77-106">Le eccezioni, ovvero le transazioni sintetiche che richiedono istruzioni di configurazione speciali, sono illustrate nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="e0f77-106">The exceptions—synthetic transactions that require special setup instructions—are discussed in the following sections.</span></span>

<div>

## <a name="dealing-with-server-timeout-errors"></a><span data-ttu-id="e0f77-107">Gestione degli errori di timeout del server</span><span class="sxs-lookup"><span data-stu-id="e0f77-107">Dealing With Server Timeout Errors</span></span>

<span data-ttu-id="e0f77-108">In alcuni casi è possibile che le transazioni sintetiche non siano in errore con gli errori di timeout del server (codice Error 504).</span><span class="sxs-lookup"><span data-stu-id="e0f77-108">In some cases you might find that your synthetic transactions are failing with server timeout errors (error code 504).</span></span> <span data-ttu-id="e0f77-109">Questi errori sono in genere dovuti a problemi di firewall.</span><span class="sxs-lookup"><span data-stu-id="e0f77-109">These errors are typically due to firewall problems.</span></span> <span data-ttu-id="e0f77-110">Quando viene eseguita una transazione sintetica, tale transazione viene eseguita nel processo MonitoringHost. exe; a sua volta, MonitoringHost. exe avvia un'istanza del processo PowerShell. exe.</span><span class="sxs-lookup"><span data-stu-id="e0f77-110">When a synthetic transaction is executed, that transaction runs under the MonitoringHost.exe process; in turn, MonitoringHost.exe starts an instance of the PowerShell.exe process.</span></span> <span data-ttu-id="e0f77-111">Se MonitoringHost. exe o PowerShell. exe viene bloccato dal firewall, la transazione sintetica non riesce e genererà un errore di 504.</span><span class="sxs-lookup"><span data-stu-id="e0f77-111">If either MonitoringHost.exe or PowerShell.exe is blocked by your firewall then the synthetic transaction will fail and will generate a 504 error.</span></span>

<span data-ttu-id="e0f77-112">Per risolvere il problema, è consigliabile creare manualmente regole firewall in ingresso sia per MonitoringHost. exe che per PowerShell. exe nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="e0f77-112">To resolve this issue, you should manually create inbound firewall rules for both MonitoringHost.exe and PowerShell.exe on the local machine.</span></span> <span data-ttu-id="e0f77-113">Questa operazione può essere eseguita tramite Windows Firewall o un software firewall locale di terze parti, a seconda della configurazione preesistente del server.</span><span class="sxs-lookup"><span data-stu-id="e0f77-113">This can be done via Windows firewall or a third-party local firewall software, depending on your server's preexisting configuration.</span></span>

<span data-ttu-id="e0f77-114">Se si usa un dispositivo firewall di rete tra il computer host delle transazioni sintetiche e i server Lync che si sta tentando di monitorare, è consigliabile trattare l'host come computer client e osservare tutti i requisiti della porta del firewall da [porte e protocolli per i server interni in Lync server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span><span class="sxs-lookup"><span data-stu-id="e0f77-114">If you're employing a network firewall device between the synthetic transaction host machine and the Lync Servers you're attempting to monitor, you should treat the host as a client machine, and observer all firewall port requirements from [Ports and protocols for internal servers in Lync Server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).</span></span>

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a><span data-ttu-id="e0f77-115">Transazioni sintetiche per i servizi di conferenza dati</span><span class="sxs-lookup"><span data-stu-id="e0f77-115">Data Conferencing Synthetic Transactions</span></span>

<span data-ttu-id="e0f77-116">Se il computer del nodo Watcher si trova all'esterno della rete perimetrale, probabilmente non sarà possibile eseguire la transazione sintetica per i servizi di conferenza dati a meno che non vengano prima disabilitate le impostazioni proxy di Internet Explorer per l'account del servizio di rete.</span><span class="sxs-lookup"><span data-stu-id="e0f77-116">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Internet Explorer proxy settings for the Network Service account.</span></span> <span data-ttu-id="e0f77-117">Per disabilitare le impostazioni proxy per questo servizio, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="e0f77-117">To disable the proxy settings for this service, complete the following procedure:</span></span>

1.  <span data-ttu-id="e0f77-118">Nel computer del nodo Watcher fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Accessori**, fare clic con il pulsante destro del mouse su **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="e0f77-118">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="e0f77-119">Nella finestra della console digitare il comando seguente e quindi premere INVIO:</span><span class="sxs-lookup"><span data-stu-id="e0f77-119">In the console window, type the following command and then press ENTER:</span></span>
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

<span data-ttu-id="e0f77-120">Nella finestra di comando verrà visualizzato il messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="e0f77-120">The following message will appear in the command window:</span></span>

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

<span data-ttu-id="e0f77-121">Questo messaggio indica che sono state disabilitate le impostazioni proxy di Internet Explorer per l'account del servizio di rete.</span><span class="sxs-lookup"><span data-stu-id="e0f77-121">This message means that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a><span data-ttu-id="e0f77-122">Transazioni sintetiche di messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="e0f77-122">Exchange Unified Messaging Synthetic Transactions</span></span>

<span data-ttu-id="e0f77-123">La transazione sintetica della messaggistica unificata di Exchange verifica che gli utenti di test possano connettersi agli account della segreteria telefonica in Exchange.</span><span class="sxs-lookup"><span data-stu-id="e0f77-123">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span> <span data-ttu-id="e0f77-124">Questi utenti di test dovranno essere preconfigurati con gli account della segreteria telefonica prima di poter usare i test di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="e0f77-124">These test users will need to be preconfigured with voicemail accounts before they can use the Exchange UM tests.</span></span>

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a><span data-ttu-id="e0f77-125">Transazioni sintetiche della chat persistente</span><span class="sxs-lookup"><span data-stu-id="e0f77-125">Persistent Chat Synthetic Transactions</span></span>

<span data-ttu-id="e0f77-126">Per usare la transazione sintetica della chat persistente, gli amministratori devono prima di tutto creare un canale e concedere agli utenti di test le autorizzazioni per usarlo.</span><span class="sxs-lookup"><span data-stu-id="e0f77-126">To use the Persistent Chat synthetic transaction, administrators must first create a channel and give the test users permissions to use it.</span></span> <span data-ttu-id="e0f77-127">Il cmdlet [test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) può essere usato per configurare correttamente questi utenti di test:</span><span class="sxs-lookup"><span data-stu-id="e0f77-127">The [Test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet can be used to properly configure these test users:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

<span data-ttu-id="e0f77-128">Questa attività di configurazione deve essere eseguita dall'interno dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="e0f77-128">This setup task must be run from inside the enterprise:</span></span>

  - <span data-ttu-id="e0f77-129">Se eseguito da un computer non server, l'utente che esegue il cmdlet deve essere membro del ruolo PersistentChatAdministrators per il controllo di accesso basato sui ruoli (RBAC).</span><span class="sxs-lookup"><span data-stu-id="e0f77-129">If run from a nonserver machine, the user who runs the cmdlet must be a member of the PersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>

  - <span data-ttu-id="e0f77-130">Se eseguito dal server stesso, l'utente che esegue il cmdlet deve essere un membro del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e0f77-130">If run from the server itself, the user who runs the cmdlet should be a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="e0f77-131">Nel comando precedente il parametro Setup è stato incluso e impostato su true ($True).</span><span class="sxs-lookup"><span data-stu-id="e0f77-131">In the preceding command, the Setup parameter was included and set to True ($True).</span></span> <span data-ttu-id="e0f77-132">Se si include il parametro Setup, test-CsPersistentChatMessage creerà una chat room persistente speciale e compilerà la sala con gli utenti di test.</span><span class="sxs-lookup"><span data-stu-id="e0f77-132">If you include the Setup parameter, Test-CsPersistentChatMessage will create a special Persistent Chat room and populate that room with the test users.</span></span> <span data-ttu-id="e0f77-133">Ciò consente di verificare che in realtà sia disponibile una chat room a scopo di test.</span><span class="sxs-lookup"><span data-stu-id="e0f77-133">This helps to ensure that there is actually a chat room available for testing purposes.</span></span> <span data-ttu-id="e0f77-134">Tieni presente che il parametro Setup deve essere eseguito solo da un server front-end.</span><span class="sxs-lookup"><span data-stu-id="e0f77-134">Note that the Setup parameter should be run only from a Front End Server.</span></span>

<span data-ttu-id="e0f77-135">La chat room creata da test-CsPersistentChatMessage può essere eliminata solo da un amministratore.</span><span class="sxs-lookup"><span data-stu-id="e0f77-135">The chat room that is created by Test-CsPersistentChatMessage can be deleted only by an administrator.</span></span>

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a><span data-ttu-id="e0f77-136">Transazioni sintetiche di chiamate peer-to-peer PSTN</span><span class="sxs-lookup"><span data-stu-id="e0f77-136">PSTN Peer-to-Peer Call Synthetic Transactions</span></span>

<span data-ttu-id="e0f77-137">La transazione sintetica [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) verifica la possibilità di effettuare e ricevere chiamate tramite la rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="e0f77-137">The [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) synthetic transaction verifies the ability to place and receive calls via the public switched telephone network (PSTN).</span></span>

<span data-ttu-id="e0f77-138">Per eseguire questa transazione sintetica, gli amministratori devono configurare:</span><span class="sxs-lookup"><span data-stu-id="e0f77-138">To run this synthetic transaction, administrators must configure:</span></span>

  - <span data-ttu-id="e0f77-139">Due utenti di test (un chiamante e un ricevitore) abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="e0f77-139">Two test users (a caller and a receiver) enabled for Enterprise Voice.</span></span>

  - <span data-ttu-id="e0f77-140">Numeri DID (Direct inwarding Dialing) per ogni account utente.</span><span class="sxs-lookup"><span data-stu-id="e0f77-140">Direct Inward Dialing (DID) numbers for each user account.</span></span>

  - <span data-ttu-id="e0f77-141">Criteri vocali e route vocali che consentono alle chiamate al numero del destinatario di raggiungere il gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="e0f77-141">Voice policies and voice routes that enable calls to the receiver’s number to reach the PSTN gateway.</span></span>

  - <span data-ttu-id="e0f77-142">Un gateway PSTN che accetta chiamate e elementi multimediali che instradano le chiamate viene eseguito sul pool Home di un destinatario in base al numero composto.</span><span class="sxs-lookup"><span data-stu-id="e0f77-142">A PSTN gateway that accepts calls, and media that route calls backs to a receiver’s home pool based on the number dialed.</span></span>

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a><span data-ttu-id="e0f77-143">Transazioni sintetiche dell'archivio contatti unificato</span><span class="sxs-lookup"><span data-stu-id="e0f77-143">Unified Contact Store Synthetic Transactions</span></span>

<span data-ttu-id="e0f77-144">La transazione sintetica dell'archivio contatti unificato verifica che Lync Server 2013 sia in grado di recuperare i contatti per conto di un utente da Microsoft Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e0f77-144">The Unified Contact Store synthetic transaction verifies that Lync Server 2013 is able to retrieve contacts on behalf of a user from Microsoft Exchange Server 2013.</span></span>

<span data-ttu-id="e0f77-145">Per usare questa transazione sintetica, è necessario che siano soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0f77-145">To use this synthetic transaction, the following conditions must be met:</span></span>

  - <span data-ttu-id="e0f77-146">La [gestione dell'autenticazione server-Server (OAuth) e delle applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) deve essere configurata tra lync Server 2013 ed Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="e0f77-146">[Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) must be configured between Lync Server 2013 and Exchange 2013.</span></span>

  - <span data-ttu-id="e0f77-147">Test gli utenti devono avere una cassetta postale di Exchange 2013 valida.</span><span class="sxs-lookup"><span data-stu-id="e0f77-147">Test users must have a valid Exchange 2013 mailbox.</span></span>

<span data-ttu-id="e0f77-148">Una volta soddisfatte queste condizioni, gli amministratori possono eseguire il comando seguente per verificare che l'utente con l'indirizzo SIP kenmyer@litwareinc.com possa recuperare i contatti dall'archivio contatti unificato:</span><span class="sxs-lookup"><span data-stu-id="e0f77-148">After these conditions are met, administrators can run the following command to verify that the user with the SIP address kenmyer@litwareinc.com can retrieve his contacts from the unified contact store:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

<span data-ttu-id="e0f77-149">Nota l'uso del parametro Setup usato nel comando precedente.</span><span class="sxs-lookup"><span data-stu-id="e0f77-149">Note the use of the Setup parameter used in the preceding command.</span></span> <span data-ttu-id="e0f77-150">Se il parametro Setup viene incluso durante l'uso di Test-CsUnifiedContactStore, i contatti dell'utente specificato (in questo caso sip:kenmyer@litwareinc.com) verranno spostati nell'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="e0f77-150">If the Setup parameter is included when running Test-CsUnifiedContactStore then the specified user’s contacts (in this case, sip:kenmyer@litwareinc.com) will be moved to the unified contact store.</span></span> <span data-ttu-id="e0f77-151">Naturalmente, se i contatti dell'utente sono già presenti nell'archivio contatti unificato, non è necessario spostarli. Il parametro Setup viene in genere usato solo una volta (la prima volta che viene eseguito test-CsUnifiedContactStore) e deve essere usato solo con gli utenti di test. con gli account utente che non avranno mai effettivamente eseguito l'accesso a Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e0f77-151">(Of course, if the user’s contacts are already in the Unified Contact Store then they do not have to be moved.) The Setup parameter is typically used only one time (the first time Test-CsUnifiedContactStore is executed), and should only be used with test users; that is, with user accounts that will never actually be logged on to Lync Server.</span></span> <span data-ttu-id="e0f77-152">Dopo che l'utente di test è stato migrato nell'archivio contatti unificato, è possibile verificare che i contatti dell'utente possano essere recuperati chiamando Test-CsUnifiedContactStore senza il parametro Setup:</span><span class="sxs-lookup"><span data-stu-id="e0f77-152">After your test user has been migrated to the unified contact store, you can verify that the user’s contacts can be retrieved by calling Test-CsUnifiedContactStore without the Setup parameter:</span></span>

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a><span data-ttu-id="e0f77-153">Transazioni sintetiche XMPP</span><span class="sxs-lookup"><span data-stu-id="e0f77-153">XMPP Synthetic Transactions</span></span>

<span data-ttu-id="e0f77-154">Il protocollo XMPP (Extensible Messaging and Presence Protocol) la transazione sintetica di messaggistica istantanea richiede che la caratteristica XMPP sia configurata con uno o più domini federati.</span><span class="sxs-lookup"><span data-stu-id="e0f77-154">The XMPP (Extensible Messaging and Presence Protocol) IM synthetic transaction requires that the XMPP feature be configured with one or more federated domains.</span></span>

<span data-ttu-id="e0f77-155">Per abilitare la transazione sintetica XMPP, è necessario che venga fornito un parametro XmppTestReceiverMailAddress con un account utente in un dominio XMPP instradabile.</span><span class="sxs-lookup"><span data-stu-id="e0f77-155">To enable the XMPP synthetic transaction, an XmppTestReceiverMailAddress parameter must be provided with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="e0f77-156">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e0f77-156">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

<span data-ttu-id="e0f77-157">In questo esempio, sarà necessario disporre di una regola Lync Server 2013 per instradare i messaggi per litwareinc.com a un gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="e0f77-157">In this example, a Lync Server 2013 rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

