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

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a>Istruzioni per la configurazione speciale per le transazioni sintetiche in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-11-16_

La maggior parte delle transazioni sintetiche può essere eseguita in un nodo Watcher così com'è; ovvero, non appena la transazione sintetica è stata aggiunta alle impostazioni di configurazione del nodo Watcher, il nodo Watcher può iniziare a usare la transazione sintetica durante le sessioni di test. Tuttavia, questo non è vero per tutte le transazioni sintetiche. Le eccezioni, ovvero le transazioni sintetiche che richiedono istruzioni di configurazione speciali, sono illustrate nelle sezioni seguenti.

<div>

## <a name="dealing-with-server-timeout-errors"></a>Gestione degli errori di timeout del server

In alcuni casi è possibile che le transazioni sintetiche non siano in errore con gli errori di timeout del server (codice Error 504). Questi errori sono in genere dovuti a problemi di firewall. Quando viene eseguita una transazione sintetica, tale transazione viene eseguita nel processo MonitoringHost. exe; a sua volta, MonitoringHost. exe avvia un'istanza del processo PowerShell. exe. Se MonitoringHost. exe o PowerShell. exe viene bloccato dal firewall, la transazione sintetica non riesce e genererà un errore di 504.

Per risolvere il problema, è consigliabile creare manualmente regole firewall in ingresso sia per MonitoringHost. exe che per PowerShell. exe nel computer locale. Questa operazione può essere eseguita tramite Windows Firewall o un software firewall locale di terze parti, a seconda della configurazione preesistente del server.

Se si usa un dispositivo firewall di rete tra il computer host delle transazioni sintetiche e i server Lync che si sta tentando di monitorare, è consigliabile trattare l'host come computer client e osservare tutti i requisiti della porta del firewall da [porte e protocolli per i server interni in Lync server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a>Transazioni sintetiche per i servizi di conferenza dati

Se il computer del nodo Watcher si trova all'esterno della rete perimetrale, probabilmente non sarà possibile eseguire la transazione sintetica per i servizi di conferenza dati a meno che non vengano prima disabilitate le impostazioni proxy di Internet Explorer per l'account del servizio di rete. Per disabilitare le impostazioni proxy per questo servizio, eseguire la procedura seguente:

1.  Nel computer del nodo Watcher fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Accessori**, fare clic con il pulsante destro del mouse su **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.

2.  Nella finestra della console digitare il comando seguente e quindi premere INVIO:
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

Nella finestra di comando verrà visualizzato il messaggio seguente:

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

Questo messaggio indica che sono state disabilitate le impostazioni proxy di Internet Explorer per l'account del servizio di rete.

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a>Transazioni sintetiche di messaggistica unificata di Exchange

La transazione sintetica della messaggistica unificata di Exchange verifica che gli utenti di test possano connettersi agli account della segreteria telefonica in Exchange. Questi utenti di test dovranno essere preconfigurati con gli account della segreteria telefonica prima di poter usare i test di messaggistica unificata di Exchange.

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a>Transazioni sintetiche della chat persistente

Per usare la transazione sintetica della chat persistente, gli amministratori devono prima di tutto creare un canale e concedere agli utenti di test le autorizzazioni per usarlo. Il cmdlet [test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) può essere usato per configurare correttamente questi utenti di test:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

Questa attività di configurazione deve essere eseguita dall'interno dell'organizzazione:

  - Se eseguito da un computer non server, l'utente che esegue il cmdlet deve essere membro del ruolo PersistentChatAdministrators per il controllo di accesso basato sui ruoli (RBAC).

  - Se eseguito dal server stesso, l'utente che esegue il cmdlet deve essere un membro del gruppo RTCUniversalServerAdmins.

Nel comando precedente il parametro Setup è stato incluso e impostato su true ($True). Se si include il parametro Setup, test-CsPersistentChatMessage creerà una chat room persistente speciale e compilerà la sala con gli utenti di test. Ciò consente di verificare che in realtà sia disponibile una chat room a scopo di test. Tieni presente che il parametro Setup deve essere eseguito solo da un server front-end.

La chat room creata da test-CsPersistentChatMessage può essere eliminata solo da un amministratore.

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a>Transazioni sintetiche di chiamate peer-to-peer PSTN

La transazione sintetica [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) verifica la possibilità di effettuare e ricevere chiamate tramite la rete PSTN (Public Switched Telephone Network).

Per eseguire questa transazione sintetica, gli amministratori devono configurare:

  - Due utenti di test (un chiamante e un ricevitore) abilitati per VoIP aziendale.

  - Numeri DID (Direct inwarding Dialing) per ogni account utente.

  - Criteri vocali e route vocali che consentono alle chiamate al numero del destinatario di raggiungere il gateway PSTN.

  - Un gateway PSTN che accetta chiamate e elementi multimediali che instradano le chiamate viene eseguito sul pool Home di un destinatario in base al numero composto.

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a>Transazioni sintetiche dell'archivio contatti unificato

La transazione sintetica dell'archivio contatti unificato verifica che Lync Server 2013 sia in grado di recuperare i contatti per conto di un utente da Microsoft Exchange Server 2013.

Per usare questa transazione sintetica, è necessario che siano soddisfatte le condizioni seguenti:

  - La [gestione dell'autenticazione server-Server (OAuth) e delle applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) deve essere configurata tra lync Server 2013 ed Exchange 2013.

  - Test gli utenti devono avere una cassetta postale di Exchange 2013 valida.

Una volta soddisfatte queste condizioni, gli amministratori possono eseguire il comando seguente per verificare che l'utente con l'indirizzo SIP kenmyer@litwareinc.com possa recuperare i contatti dall'archivio contatti unificato:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

Nota l'uso del parametro Setup usato nel comando precedente. Se il parametro Setup viene incluso durante l'uso di Test-CsUnifiedContactStore, i contatti dell'utente specificato (in questo caso sip:kenmyer@litwareinc.com) verranno spostati nell'archivio contatti unificato. Naturalmente, se i contatti dell'utente sono già presenti nell'archivio contatti unificato, non è necessario spostarli. Il parametro Setup viene in genere usato solo una volta (la prima volta che viene eseguito test-CsUnifiedContactStore) e deve essere usato solo con gli utenti di test. con gli account utente che non avranno mai effettivamente eseguito l'accesso a Lync Server. Dopo che l'utente di test è stato migrato nell'archivio contatti unificato, è possibile verificare che i contatti dell'utente possano essere recuperati chiamando Test-CsUnifiedContactStore senza il parametro Setup:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a>Transazioni sintetiche XMPP

Il protocollo XMPP (Extensible Messaging and Presence Protocol) la transazione sintetica di messaggistica istantanea richiede che la caratteristica XMPP sia configurata con uno o più domini federati.

Per abilitare la transazione sintetica XMPP, è necessario che venga fornito un parametro XmppTestReceiverMailAddress con un account utente in un dominio XMPP instradabile. Ad esempio:

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

In questo esempio, sarà necessario disporre di una regola Lync Server 2013 per instradare i messaggi per litwareinc.com a un gateway XMPP.

</div>

</div>

<span> </span>

</div>

</div>

</div>

