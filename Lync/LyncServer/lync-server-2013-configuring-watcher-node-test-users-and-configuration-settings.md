---
title: Configurazione degli utenti e delle impostazioni di configurazione di testing node Watcher
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
ms.openlocfilehash: a3713844d5d2364459a28c5919bb1d32d421d706
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733666"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a>Configurazione degli utenti e delle impostazioni di configurazione di testing node di Watcher in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-07-29_

Dopo aver configurato il computer che fungerà da nodo Watcher, è necessario:

1.  Creare gli account di test da usare in questi nodi Watcher. Se si usa il metodo di autenticazione Negotiate, è necessario usare anche il cmdlet [Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)) per abilitare questi account di test per l'uso nel nodo Watcher.

2.  Aggiornare le impostazioni di configurazione dei nodi Watcher.

Questa sezione illustra:

  - Configurazione degli account utente di test

  - Configurazione di un nodo Watcher di base con le transazioni sintetiche predefinite

  - Configurazione di test estesi

  - Aggiunta e rimozione di transazioni sintetiche

  - Visualizzazione e test della configurazione dei nodi Watcher

<div>

## <a name="configuring-test-user-accounts"></a>Configurazione degli account utente di test

Gli utenti di test non devono rappresentare persone effettive, ma devono essere account di servizi di dominio Active Directory validi. Inoltre, questi account devono essere abilitati per Lync Server 2013, devono avere indirizzi SIP validi e devono essere abilitati per Enterprise Voice (per usare la transazione sintetica Test-CsPstnPeerToPeerCall). Se usi il metodo di autenticazione TrustedServer, devi solo assicurarti che questi account esistano e siano stati configurati come specificato qui. È consigliabile assegnare almeno tre utenti di test per ogni pool che si vuole testare.

Se si usa il metodo di autenticazione Negotiate, è necessario usare anche il cmdlet **Set-CsTestUserCredential** e Lync Server Management Shell per consentire agli account di test di lavorare con le transazioni sintetiche. Puoi eseguire questa operazione eseguendo un comando simile al seguente. Questi comandi presuppongono che i tre account utente di Active Directory siano già stati creati e che questi account siano stati abilitati per Lync Server 2013.):

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

Tieni presente che devi includere non solo l'indirizzo SIP, ma anche il nome utente e la password. Se non si include il set di password, CsTestUserCredential verrà richiesto di immettere le informazioni. Il nome utente può essere specificato usando il formato del\\nome utente del nome di dominio mostrato sopra oppure usando il formato user name@domain name; Per esempio:

    -UserName "watcher3@litwareinc.com"

Per verificare che le credenziali utente di test siano state create, eseguire questi comandi dall'interno di Lync Server Management Shell:

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

Le informazioni simili a queste devono essere restituite per ogni utente:

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>Configurazione di un nodo Watcher di base con le transazioni sintetiche predefinite

Dopo aver creato gli utenti di test, puoi creare un nodo Watcher usando un comando simile al seguente:

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

Questo comando crea un nuovo nodo Watcher che usa le impostazioni predefinite ed esegue il set predefinito di transazioni sintetiche. Il nuovo nodo Watcher usa anche gli utenti di test watcher1@litwareinc.com, watcher2@litwareinc.com e watcher3@litwareinc.com. Se il nodo Watcher usa l'autenticazione TrustedServer, i tre account di test possono essere tutti gli account utente validi abilitati per Active Directory e Lync Server. Se il nodo Watcher usa il metodo di autenticazione Negotiate, devi anche abilitare questi account utente per il nodo Watcher usando il cmdlet **Set-CsTestUserCredential** .

</div>

<div>

## <a name="configuring-extended-tests"></a>Configurazione di test estesi

Se si vuole abilitare la rete PSTN (Public Switched Telephone Network), che verifica la connettività con la rete telefonica pubblica commutata, è necessario eseguire alcune configurazioni aggiuntive durante la configurazione del nodo Watcher. Prima di tutto, è necessario associare gli utenti di test al tipo di test PSTN. A questo scopo, Esegui un comando simile a questo dall'interno di Lync Server Management Shell:

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

Tieni presente che i risultati di questo comando devono essere archiviati in una variabile. In questo esempio si tratta di una variabile denominata $pstnTest.

A questo punto, puoi usare il cmdlet **New-CsWatcherNodeConfiguration** per associare il tipo di test (archiviato nella variabile $pstnTest) a un pool di Lync Server 2013. Ad esempio, il comando seguente crea una nuova configurazione di nodi Watcher per il pool atl-cs-001.litwareinc.com, aggiungendo i tre utenti di test creati in precedenza e aggiungendo anche il tipo di test PSTN:

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

Tieni presente che il comando precedente non riesce se non hai installato i file di base di Lync Server e il database di RTCLocal nel computer del nodo Watcher.

Per testare più criteri vocali, è necessario creare un test esteso per ogni criterio usando il cmdlet **New-CsExtendedTest** . Gli utenti assegnati a questo test devono essere configurati con i criteri vocali desiderati. I test estesi vengono quindi passati al cmdlet **New-CsWatcherNodeConfiguration** usando un comando simile al seguente:

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

Se New-CsWatcherNodeConfiguration viene chiamato senza usare il parametro tests, significa che solo le transazioni sintetiche predefinite (e la transazione sintetica estesa specificata) verranno abilitate per il nuovo nodo Watcher. Questo significa che il nodo Watcher testerà i componenti seguenti:

  - Registrazione

  - Messaggistica istantanea

  - GroupIM

  - P2PAV (sessioni audio/video peer-to-peer)

  - AvConference (audio/servizi di conferenza)

  - Icone di presenza

  - ABS (servizio Rubrica)

  - ABWQ (servizio Web Rubrica)

  - PSTN (chiamate gateway PSTN, specificate come test esteso. Per impostazione predefinita, PSTN è disabilitato. Il test è abilitato in questo caso solo perché il comando ha abilitato la rete PSTN usando il parametro ExtendedTests.

Ciò significa anche che i componenti seguenti non verranno testati per impostazione predefinita:

  - AVEdgeConnectivity

  - MCXP2PIM (dispositivo mobile Instant Messaging)

  - ExumConnectivity (messaggistica unificata di Exchange)

  - JoinLauncher

  - PersistentChatMessage

  - Dataconference

  - XmppIM

  - UnifiedContactStore

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a>Aggiunta e rimozione di transazioni sintetiche

Dopo aver configurato un nodo Watcher, è possibile usare il cmdlet **set-CsWatcherNodeConfiguration** per aggiungere o rimuovere transazioni sintetiche dal nodo. Ad esempio, per aggiungere il test PersistentChatMessage al nodo Watcher, usa il metodo Add e un comando simile al seguente:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

È possibile aggiungere più test separando i nomi dei test usando le virgole. Ad esempio:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

Si noti che si verificherà un errore se uno o più di questi test, ad esempio dataconference, sono già stati abilitati nel nodo Watcher. In questo caso, viene visualizzato un messaggio di errore simile al seguente:

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

Quando si verifica questo errore, non verrà applicata alcuna modifica. Il comando deve essere ripetuto con il test duplicato rimosso.

Per rimuovere una transazione sintetica da un nodo Watcher, usa il metodo Remove invece del metodo Add. Ad esempio, questo comando rimuove il test ABWQ da un nodo Watcher:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

Puoi anche usare il metodo Replace per sostituire tutti i test attualmente abilitati con uno o più nuovi test. Ad esempio, se si vuole che un nodo Watcher esegua il test di messaggistica istantanea, è possibile configurarlo usando questo comando:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

Quando si esegue il comando precedente, tutte le transazioni sintetiche del nodo Watcher specificato verranno disabilitate ad eccezione di messaggistica istantanea.

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a>Visualizzazione e test della configurazione dei nodi Watcher

Se si vogliono visualizzare i test assegnati a un nodo Watcher, usare un comando simile al seguente:

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

Il comando precedente restituirà informazioni simili a queste, a seconda delle transazioni sintetiche assegnate al nodo:

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
> Per visualizzare le transazioni sintetiche in ordine alfabetico, USA invece questo comando:<BR>Get-CsWatcherNodeConfiguration – Identity "atl-cs-001.litwareinc.com" | Select-Object-test ExpandProperty | Oggetto ordinamento



</div>

Per verificare che sia stato creato un nodo Watcher, digitare il comando seguente all'interno di Lync Server Management Shell:

    Get-CsWatcherNodeConfiguration

Verranno ricevute informazioni simili a queste:

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

Per verificare che il nodo Watcher sia stato configurato correttamente, digitare il comando seguente all'interno di Lync Server Management Shell:

    Test-CsWatcherNodeConfiguration

Il comando precedente testerà ogni nodo Watcher nella distribuzione e fornirà informazioni, ad esempio se:

  - Il ruolo di registrar richiesto è stato installato.

  - La chiave del registro di sistema necessaria è stata creata per l'utente quando è stato eseguito set-CsWatcherNodeConfiguration.

  - I server stanno usando la versione corretta di Lync Server.

  - Le porte sono state configurate correttamente.

  - Gli utenti di test assegnati hanno le credenziali necessarie.

</div>

</div>

<span> </span>

</div>

</div>

</div>

