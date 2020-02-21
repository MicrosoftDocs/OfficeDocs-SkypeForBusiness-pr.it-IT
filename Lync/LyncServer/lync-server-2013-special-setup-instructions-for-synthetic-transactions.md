---
title: 'Lync Server 2013: istruzioni di installazione speciali per le transazioni sintetiche'
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
ms.openlocfilehash: defed8a0356d489a628f883b42ae658aadd6442d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a>Istruzioni di installazione speciali per le transazioni sintetiche in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-11-16_

La maggior parte delle transazioni sintetiche può essere eseguita su un nodo Watcher così com'è, ovvero non appena la transazione sintetica viene aggiunta alle impostazioni di configurazione del nodo Watcher, questo può iniziare a utilizzarla durante l'esecuzione di test. Ciò non è vero, tuttavia, per tutte le transazioni sintetiche. Nelle sezioni seguenti vengono descritte le eccezioni, ovvero le transazioni sintetiche con istruzioni speciali per la configurazione.

<div>

## <a name="dealing-with-server-timeout-errors"></a>Gestione degli errori di timeout del server

In alcuni casi, è possibile che le transazioni sintetiche non siano in grado di ottenere errori di timeout del server (codice di errore 504). Questi errori in genere sono dovuti a problemi di firewall. Quando viene eseguita una transazione sintetica, tale transazione viene eseguita con il processo MonitoringHost. exe. a sua incirca, MonitoringHost. exe avvia un'istanza del processo PowerShell. exe. Se MonitoringHost. exe o PowerShell. exe viene bloccato dal firewall, la transazione sintetica avrà esito negativo e genererà un errore 504.

Per risolvere il problema, è necessario creare manualmente le regole del firewall in ingresso sia per MonitoringHost. exe che per PowerShell. exe nel computer locale. A seconda della configurazione preesistente del server, è possibile farlo tramite Windows Firewall o un software firewall locale di terze parti.

Se si utilizza un dispositivo firewall di rete tra il computer host delle transazioni sintetiche e i server Lync che si sta tentando di monitorare, è consigliabile considerare l'host come un computer client e osservare tutti i requisiti delle porte del firewall provenienti da [porte e protocolli per i server interni in Lync server 2013](lync-server-2013-ports-and-protocols-for-internal-servers.md).

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a>Transazioni sintetiche per conferenze dati

Se il computer del nodo Watcher si trova all'esterno della rete perimetrale, è probabile che non sia possibile eseguire la transazione sintetica di conferenza dati a meno che non siano state prima disabilitate le impostazioni del proxy di Internet Explorer per l'account di servizio di rete. Per disabilitare le impostazioni proxy per questo servizio, eseguire la procedura seguente:

1.  Nel computer del nodo Watcher fare clic su **Start**, scegliere **Tutti i programmi**, **Accessori**, quindi fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.

2.  Nella finestra della console digitare il comando seguente, quindi premere INVIO.
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

Nella finestra di comando verrà visualizzato il messaggio seguente:

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

Questo messaggio indica che sono state disabilitate le impostazioni del proxy di Internet Explorer per l'account di servizio di rete.

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a>Transazioni sintetiche per la messaggistica unificata di Exchange.

La transazione sintetica di messaggistica unificata di Exchange verifica che gli utenti di test siano in grado di connettersi agli account della segreteria telefonica ospitati in Exchange. È necessario configurare tali utenti di prova con account per la segreteria telefonia prima che possano utilizzare i test di messaggistica unificata di Exchange.

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a>Transazioni sintetiche di chat persistente

Per utilizzare la transazione sintetica Persistent Chat, gli amministratori devono innanzitutto creare un canale e concedere alle autorizzazioni agli utenti di test di utilizzarlo. Il cmdlet [test-CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) può essere utilizzato per configurare correttamente gli utenti di test:

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

Questa attività di configurazione deve essere eseguita dall'interno dell'organizzazione:

  - Se l'attività viene eseguita da un computer non server, l'utente che esegue il cmdlet deve essere membro del ruolo PersistentChatAdministrators per il controllo di accesso basato sui ruoli (RBAC).

  - Se l'attività viene eseguita dal server stesso, l'utente che esegue il cmdlet deve essere un membro del gruppo RTCUniversalServerAdmins.

Nel comando precedente è incluso il parametro Setup impostato su True ($True). Se si include il parametro Setup, test-CsPersistentChatMessage creerà una chat room persistente speciale e compilerà tale sala con gli utenti di test. Ciò consente di assicurarsi che sia effettivamente disponibile una chat room per i test. Si noti che il parametro Setup deve essere eseguito solo da un front end server.

La chat room creata da Test-CsPersistentChatMessage può essere eliminata solo da un amministratore.

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a>Transazioni sintetiche per chiamate peer-to-peer PSTN

La transazione sintetica [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) verifica la possibilità di effettuare e ricevere chiamate tramite la rete PSTN (Public Switched Telephone Network).

Per eseguire questa transazione sintetica, gli amministratori devono configurare:

  - Due utenti di test (un chiamante e un destinatario) abilitati per VoIP aziendale.

  - Numeri DID (Direct Inward Dialing) per ogni account utente.

  - Criteri vocali e route vocali per consentire alle chiamate al numero del ricevente di raggiungere il gateway PSTN.

  - Un gateway PSTN che accetta le chiamate e un supporto per il routing delle chiamate al pool principale del ricevente in base al numero composto.

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a>Transazioni sintetiche per l'archivio contatti unificato

La transazione sintetica archivio contatti unificato verifica che Lync Server 2013 sia in grado di recuperare i contatti per conto di un utente da Microsoft Exchange Server 2013.

Per utilizzare questa transazione sintetica, devono essere soddisfatte le condizioni seguenti:

  - La [gestione dell'autenticazione da server a server (OAuth) e delle applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) deve essere configurata tra lync Server 2013 ed Exchange 2013.

  - Gli utenti di test devono disporre di una cassetta postale di Exchange 2013 valida.

Quando queste condizioni sono soddisfatte, gli amministratori possono eseguire il comando seguente per verificare che l'utente con indirizzo SIP kenmyer@litwareinc.com possa recuperare i contatti personali dall'archivio contatti unificato:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

Si noti l'utilizzo del parametro Setup nel comando precedente. Se si include il parametro Setup durante l'esecuzione di Test-CsUnifiedContactStore, i contatti dell'utente specificato (in questo caso, sip:kenmyer@litwareinc.com) verranno spostati nell'archivio contatti unificato. Naturalmente, se i contatti dell'utente sono già presenti nell'archivio contatti unificato, non è necessario spostarli. Il parametro Setup viene in genere utilizzato solo una volta, ovvero la prima volta che viene eseguito test-CsUnifiedContactStore, e deve essere utilizzato solo con gli utenti di test. con gli account utente che non verranno mai effettivamente connessi a Lync Server. Al termine della migrazione dei contatti dell'utente di prova nell'archivio contatti unificato, è possibile verificare che i contatti dell'utente possano essere recuperati, chiamando Test-CsUnifiedContactStore senza il parametro Setup:

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a>Transazioni sintetiche per XMPP

La transazione sintetica per la messaggistica istantanea XMPP (Extensible Messaging and Presence Protocol) richiede la configurazione della funzionalità XMPP in uno o più domini federati.

Per abilitare la transazione sintetica XMPP, è necessario specificare un parametro XmppTestReceiverMailAddress con un account utente come dominio XMPP instradabile. Ad esempio:

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

In questo esempio, è necessario che esista una regola di Lync Server 2013 per instradare i messaggi per litwareinc.com a un gateway XMPP.

</div>

</div>

<span> </span>

</div>

</div>

</div>

