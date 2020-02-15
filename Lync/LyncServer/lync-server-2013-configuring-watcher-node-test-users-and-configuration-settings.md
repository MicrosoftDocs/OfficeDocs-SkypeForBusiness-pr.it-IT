---
title: Configurazione degli utenti e delle impostazioni di configurazione del nodo Watcher
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5373984e3a4349d73974d9f3b6c243999fbb165
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a>Configurazione degli utenti e delle impostazioni di configurazione del nodo Watcher in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-07-29_

Dopo avere configurato il computer che fungerà da nodo Watcher, è necessario eseguire le operazioni seguenti:

1.  Creare gli account di test che devono essere utilizzati da questi nodi Watcher. Se si utilizza il metodo di autenticazione Negotiate, è inoltre necessario utilizzare il cmdlet [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) per abilitare questi account di test per l'utilizzo nel nodo Watcher.

2.  Aggiornare le impostazioni di configurazione del nodo Watcher.

In questa sezione vengono trattati i temi seguenti:

  - Configurazione degli account utente di test

  - Configurazione di un nodo Watcher di base con le transazioni sintetiche predefinite

  - Configurazione dei test estesi

  - Aggiunta e rimozione di transazioni sintetiche

  - Visualizzazione e verifica della configurazione del nodo Watcher

<div>

## <a name="configuring-test-user-accounts"></a>Configurazione degli account utente di test

Gli utenti di test non devono rappresentare persone effettive, ma devono essere account di servizi di dominio Active Directory validi; Inoltre, questi account devono essere abilitati per Lync Server 2013, devono disporre di indirizzi SIP validi e devono essere abilitati per VoIP aziendale (per utilizzare la transazione sintetica Test-CsPstnPeerToPeerCall). Se si utilizza il metodo di autenticazione TrustedServer, è necessario fare in modo che questi account esistano e siano stati configurati come indicato di seguito. È consigliabile assegnare almeno tre utenti di test per ogni pool che si desidera testare.

Se si utilizza il metodo di autenticazione Negotiate, è necessario utilizzare anche il cmdlet **Set-CsTestUserCredential** e Lync Server Management Shell per consentire l'utilizzo di tali account con le transazioni sintetiche. A tale scopo, è possibile eseguire un comando simile al seguente. (Questi comandi presumono che i tre account utente di Active Directory siano già stati creati e che tali account siano stati abilitati per Lync Server 2013):

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

Tenere presente che è necessario includere non solo l'indirizzo SIP, ma anche il nome utente e la password. Se non si include la password Set-CsTestUserCredential verrà chiesto di immettere tali informazioni. Il nome utente può essere specificato utilizzando il formato nome\\utente di dominio visualizzato in alto oppure utilizzando il formato utente name@domain nome; Per esempio:

    -UserName "watcher3@litwareinc.com"

Per verificare che le credenziali dell'utente di test siano state create, eseguire questi comandi dall'interno di Lync Server Management Shell:

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

Per ogni utente verranno restituite informazioni simili alle seguenti:

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Configurazione di un nodo Watcher di base con le transazioni sintetiche predefinite

Dopo avere creato gli utenti di test, è possibile creare un nodo Watcher utilizzando un comando simile al seguente:

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

Questo comando crea un nuovo nodo Watcher che utilizza le impostazioni predefinite ed esegue il set predefinito di transazioni sintetiche. Il nuovo nodo Watcher inoltre utilizza gli utenti di test watcher1@litwareinc.com, watcher2@litwareinc.com e watcher3@litwareinc.com. Se il nodo Watcher utilizza l'autenticazione di TrustedServer, i tre account di test possono essere tutti gli account utente validi abilitati per Active Directory e Lync Server. Se il nodo Watcher utilizza il metodo di autenticazione Negotiate, è inoltre necessario abilitare tali account utente per il nodo Watcher mediante il cmdlet **Set-CsTestUserCredential**.

</div>

<div>

## <a name="configuring-extended-tests"></a>Configurazione dei test estesi

Se si desidera abilitare il test PSTN, che verifica la connettività alla rete PSTN (Public Switched Telephone Network), sarà necessario eseguire alcune attività di configurazione aggiuntive durante l'impostazione del nodo Watcher. È innanzitutto necessario associare gli utenti di test al tipo di test PSTN. A tale scopo, eseguire un comando simile al seguente dall'interno di Lync Server Management Shell:

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

I risultati di questo comando devono essere archiviati in una variabile. In questo esempio la variabile è denominata $pstnTest.

A questo punto, è possibile utilizzare il cmdlet **New-CsWatcherNodeConfiguration** per associare il tipo di test (archiviato nella variabile $pstnTest) a un pool di Lync Server 2013. Il comando seguente ad esempio crea la configurazione di un nuovo nodo Watcher per il pool atl-cs-001.litwareinc.com, aggiungendo i tre utenti di test creati in precedenza e il tipo di test PSTN:

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

Si noti che il comando precedente avrà esito negativo se non sono stati installati i file di base di Lync Server e il database di RTCLocal nel computer del nodo Watcher.

Per testare più criteri vocali, è necessario creare un test esteso per ogni criterio utilizzando il cmdlet **New-CsExtendedTest**. Gli utenti assegnati a questo test devono essere configurati con i criteri vocali desiderati. I test estesi vengono quindi passati al cmdlet **New-CsWatcherNodeConfiguration** mediante un comando simile al seguente:

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

Se New-CsWatcherNodeConfiguration viene chiamato senza utilizzare il parametro Tests, solo le transazioni sintetiche predefinite e la transazione sintetica estesa specificata saranno abilitate per il nuovo nodo Watcher. Questo significa che il nodo Watcher testerà i componenti seguenti:

  - Registrazione

  - IM

  - GroupIM

  - P2PAV (Sessioni audio/video peer-to-peer)

  - AvConference (Conferenze audio)

  - Presenza

  - ABS (Servizio Rubrica)

  - ABWQ (Servizio Web Rubrica)

  - PSTN (Chiamate di gateway PSTN, specificate come test esteso. Per impostazione predefinita, il test PSTN è disabilitato. Il test è abilitato in questo caso solo perché è stato abilitato dal comando mediante l'utilizzo del parametro ExtendedTests).

Questo inoltre significa che, per impostazione predefinita, non verranno testati i componenti seguenti:

  - AVEdgeConnectivity

  - MCXP2PIM (messaggistica istantanea dei dispositivi mobili)

  - ExumConnectivity (Messaggistica unificata di Exchange)

  - JoinLauncher

  - PersistentChatMessage

  - Dataconference

  - XmppIM

  - UnifiedContactStore

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a>Aggiunta e rimozione di transazioni sintetiche

Dopo avere configurato un nodo Watcher, è possibile utilizzare il cmdlet **Set-CsWatcherNodeConfiguration** per aggiungere o rimuovere transazioni sintetiche dal nodo. Ad esempio, per aggiungere il test PersistentChatMessage al nodo Watcher, utilizzare il metodo Add e un comando simile al seguente:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

È possibile aggiungere più test separandone i nomi con le virgole. Ad esempio:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

Se uno o più di questi test, ad esempio DataConference, sono già stati abilitati per il nodo Watcher, si verificherà un errore. In questo caso verrà visualizzato un messaggio di errore simile al seguente:

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

Quando si verifica questo errore, non vengono apportate modifiche. Il comando deve essere eseguito di nuovo dopo avere rimosso il test duplicato.

Per rimuovere una transazione sintetica da un nodo Watcher, utilizzare il metodo Remove anziché il metodo Add. Ad esempio, questo comando rimuove il test ABWQ da un nodo Watcher:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

È inoltre possibile utilizzare il metodo Replace per sostituire tutti i test attualmente abilitati con uno o più test nuovi. Ad esempio, se si desidera che un nodo Watcher esegua solo il test IM, è possibile configurare questa condizione utilizzando il comando seguente:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

Quando si esegue il comando precedente, per il nodo Watcher specificato verranno disabilitate tutte le transazioni sintetiche tranne IM.

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a>Visualizzazione e verifica della configurazione del nodo Watcher

Se si desidera visualizzare i test assegnati a un nodo Watcher, utilizzare un comando simile al seguente:

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

Il comando precedente restituirà informazioni simili alle seguenti, a seconda delle transazioni sintetiche assegnate al nodo:

    Registration
    IM
    GroupIM
    P2PAV
    AvConference
    Presence
    PersistentChatMessage
    DataConference

<div>


> [!TIP]
> Per visualizzare le transazioni sintetiche in ordine alfabetico, utilizzare invece il comando seguente:<BR>Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object



</div>

Per verificare che sia stato creato un nodo Watcher, digitare il comando seguente dall'interno di Lync Server Management Shell:

    Get-CsWatcherNodeConfiguration

Verranno restituite informazioni simili alle seguenti:

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

Per verificare che il nodo Watcher sia stato configurato correttamente, digitare il comando seguente dall'interno di Lync Server Management Shell:

    Test-CsWatcherNodeConfiguration

Il comando precedente verificherà ogni nodo Watcher nella distribuzione e restituirà informazioni che indicano se:

  - Il ruolo Funzione di registrazione necessario è stato installato.

  - La chiave del Registro di sistema necessaria è stata creata automaticamente durante l'esecuzione di Set-CsWatcherNodeConfiguration.

  - I server eseguono la versione corretta di Lync Server.

  - Le porte sono state configurate correttamente.

  - Gli utenti di test assegnati dispongono delle credenziali necessarie.

</div>

</div>

<span> </span>

</div>

</div>

</div>

