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

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="b7275-102">Configurazione degli utenti e delle impostazioni di configurazione di testing node di Watcher in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7275-102">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7275-103">_**Argomento Ultima modifica:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="b7275-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="b7275-104">Dopo aver configurato il computer che fungerà da nodo Watcher, è necessario:</span><span class="sxs-lookup"><span data-stu-id="b7275-104">After configuring the computer that will act as a watcher node, you must:</span></span>

1.  <span data-ttu-id="b7275-105">Creare gli account di test da usare in questi nodi Watcher.</span><span class="sxs-lookup"><span data-stu-id="b7275-105">Create the test accounts to be used by these watcher nodes.</span></span> <span data-ttu-id="b7275-106">Se si usa il metodo di autenticazione Negotiate, è necessario usare anche il cmdlet [Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)) per abilitare questi account di test per l'uso nel nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="b7275-106">If you are using the Negotiate authentication method, you must also use the [Set-CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)) cmdlet to enable these test accounts for use on the watcher node.</span></span>

2.  <span data-ttu-id="b7275-107">Aggiornare le impostazioni di configurazione dei nodi Watcher.</span><span class="sxs-lookup"><span data-stu-id="b7275-107">Update the watcher node configuration settings.</span></span>

<span data-ttu-id="b7275-108">Questa sezione illustra:</span><span class="sxs-lookup"><span data-stu-id="b7275-108">This section covers:</span></span>

  - <span data-ttu-id="b7275-109">Configurazione degli account utente di test</span><span class="sxs-lookup"><span data-stu-id="b7275-109">Configuring Test User Accounts</span></span>

  - <span data-ttu-id="b7275-110">Configurazione di un nodo Watcher di base con le transazioni sintetiche predefinite</span><span class="sxs-lookup"><span data-stu-id="b7275-110">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

  - <span data-ttu-id="b7275-111">Configurazione di test estesi</span><span class="sxs-lookup"><span data-stu-id="b7275-111">Configuring Extended Tests</span></span>

  - <span data-ttu-id="b7275-112">Aggiunta e rimozione di transazioni sintetiche</span><span class="sxs-lookup"><span data-stu-id="b7275-112">Adding and Removing Synthetic Transactions</span></span>

  - <span data-ttu-id="b7275-113">Visualizzazione e test della configurazione dei nodi Watcher</span><span class="sxs-lookup"><span data-stu-id="b7275-113">Viewing and Testing the Watcher Node Configuration</span></span>

<div>

## <a name="configuring-test-user-accounts"></a><span data-ttu-id="b7275-114">Configurazione degli account utente di test</span><span class="sxs-lookup"><span data-stu-id="b7275-114">Configuring Test User Accounts</span></span>

<span data-ttu-id="b7275-115">Gli utenti di test non devono rappresentare persone effettive, ma devono essere account di servizi di dominio Active Directory validi. Inoltre, questi account devono essere abilitati per Lync Server 2013, devono avere indirizzi SIP validi e devono essere abilitati per Enterprise Voice (per usare la transazione sintetica Test-CsPstnPeerToPeerCall).</span><span class="sxs-lookup"><span data-stu-id="b7275-115">Test users do not need to represent actual people, but they must be valid Active Directory Domain Services accounts; in addition, these accounts must be enabled for Lync Server 2013, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> <span data-ttu-id="b7275-116">Se usi il metodo di autenticazione TrustedServer, devi solo assicurarti che questi account esistano e siano stati configurati come specificato qui.</span><span class="sxs-lookup"><span data-stu-id="b7275-116">If you use the TrustedServer authentication method, then all you need to do is to make sure that these accounts exist and have been configured as specified here.</span></span> <span data-ttu-id="b7275-117">È consigliabile assegnare almeno tre utenti di test per ogni pool che si vuole testare.</span><span class="sxs-lookup"><span data-stu-id="b7275-117">You should assign at least three test users for each pool that you want to test.</span></span>

<span data-ttu-id="b7275-118">Se si usa il metodo di autenticazione Negotiate, è necessario usare anche il cmdlet **Set-CsTestUserCredential** e Lync Server Management Shell per consentire agli account di test di lavorare con le transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="b7275-118">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet and the Lync Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="b7275-119">Puoi eseguire questa operazione eseguendo un comando simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="b7275-119">You can do this by running a command similar to the following.</span></span> <span data-ttu-id="b7275-120">Questi comandi presuppongono che i tre account utente di Active Directory siano già stati creati e che questi account siano stati abilitati per Lync Server 2013.):</span><span class="sxs-lookup"><span data-stu-id="b7275-120">(These commands assume that the three Active Directory user accounts have already been created and that those accounts have been enabled for Lync Server 2013.):</span></span>

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

<span data-ttu-id="b7275-121">Tieni presente che devi includere non solo l'indirizzo SIP, ma anche il nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="b7275-121">Note that you must include not only the SIP address but also the user name and password.</span></span> <span data-ttu-id="b7275-122">Se non si include il set di password, CsTestUserCredential verrà richiesto di immettere le informazioni.</span><span class="sxs-lookup"><span data-stu-id="b7275-122">If you do not include the password Set-CsTestUserCredential will prompt you to enter that information.</span></span> <span data-ttu-id="b7275-123">Il nome utente può essere specificato usando il formato del\\nome utente del nome di dominio mostrato sopra oppure usando il formato user name@domain name; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="b7275-123">The user name can be specified using the domain name\\user name format shown above, or by using the format user name@domain name; for example:</span></span>

    -UserName "watcher3@litwareinc.com"

<span data-ttu-id="b7275-124">Per verificare che le credenziali utente di test siano state create, eseguire questi comandi dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="b7275-124">To verify that the test user credentials were created, run these commands from within the Lync Server Management Shell:</span></span>

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

<span data-ttu-id="b7275-125">Le informazioni simili a queste devono essere restituite per ogni utente:</span><span class="sxs-lookup"><span data-stu-id="b7275-125">Information similar to this should be returned for each user:</span></span>

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="b7275-126">Configurazione di un nodo Watcher di base con le transazioni sintetiche predefinite</span><span class="sxs-lookup"><span data-stu-id="b7275-126">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="b7275-127">Dopo aver creato gli utenti di test, puoi creare un nodo Watcher usando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b7275-127">After the test users have been created you can then create a watcher node by using a command similar to this:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

<span data-ttu-id="b7275-128">Questo comando crea un nuovo nodo Watcher che usa le impostazioni predefinite ed esegue il set predefinito di transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="b7275-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="b7275-129">Il nuovo nodo Watcher usa anche gli utenti di test watcher1@litwareinc.com, watcher2@litwareinc.com e watcher3@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="b7275-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="b7275-130">Se il nodo Watcher usa l'autenticazione TrustedServer, i tre account di test possono essere tutti gli account utente validi abilitati per Active Directory e Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b7275-130">If the watcher node is using TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Lync Server.</span></span> <span data-ttu-id="b7275-131">Se il nodo Watcher usa il metodo di autenticazione Negotiate, devi anche abilitare questi account utente per il nodo Watcher usando il cmdlet **Set-CsTestUserCredential** .</span><span class="sxs-lookup"><span data-stu-id="b7275-131">If the watcher node is using the Negotiate authentication method, you must also enable these user accounts for watcher node by using the **Set-CsTestUserCredential** cmdlet.</span></span>

</div>

<div>

## <a name="configuring-extended-tests"></a><span data-ttu-id="b7275-132">Configurazione di test estesi</span><span class="sxs-lookup"><span data-stu-id="b7275-132">Configuring Extended Tests</span></span>

<span data-ttu-id="b7275-133">Se si vuole abilitare la rete PSTN (Public Switched Telephone Network), che verifica la connettività con la rete telefonica pubblica commutata, è necessario eseguire alcune configurazioni aggiuntive durante la configurazione del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="b7275-133">If you want to enable the public switched telephone network (PSTN test), which verifies connectivity with the public switched telephone network, you will need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="b7275-134">Prima di tutto, è necessario associare gli utenti di test al tipo di test PSTN.</span><span class="sxs-lookup"><span data-stu-id="b7275-134">First, you need to associate your test users with the PSTN test type.</span></span> <span data-ttu-id="b7275-135">A questo scopo, Esegui un comando simile a questo dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="b7275-135">To do that, run a command similar to this from within the Lync Server Management Shell:</span></span>

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

<span data-ttu-id="b7275-136">Tieni presente che i risultati di questo comando devono essere archiviati in una variabile.</span><span class="sxs-lookup"><span data-stu-id="b7275-136">Note that the results of this command must be stored in a variable.</span></span> <span data-ttu-id="b7275-137">In questo esempio si tratta di una variabile denominata $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="b7275-137">In this example, that's a variable named $pstnTest.</span></span>

<span data-ttu-id="b7275-138">A questo punto, puoi usare il cmdlet **New-CsWatcherNodeConfiguration** per associare il tipo di test (archiviato nella variabile $pstnTest) a un pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b7275-138">At this point, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Lync Server 2013 pool.</span></span> <span data-ttu-id="b7275-139">Ad esempio, il comando seguente crea una nuova configurazione di nodi Watcher per il pool atl-cs-001.litwareinc.com, aggiungendo i tre utenti di test creati in precedenza e aggiungendo anche il tipo di test PSTN:</span><span class="sxs-lookup"><span data-stu-id="b7275-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users that were created previously, and also adding the PSTN test type:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

<span data-ttu-id="b7275-140">Tieni presente che il comando precedente non riesce se non hai installato i file di base di Lync Server e il database di RTCLocal nel computer del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="b7275-140">Note that the preceding command will fail if you have not installed the Lync Server core files and the RTCLocal database on the watcher node computer.</span></span>

<span data-ttu-id="b7275-141">Per testare più criteri vocali, è necessario creare un test esteso per ogni criterio usando il cmdlet **New-CsExtendedTest** .</span><span class="sxs-lookup"><span data-stu-id="b7275-141">To test multiple voice policies, you need to create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="b7275-142">Gli utenti assegnati a questo test devono essere configurati con i criteri vocali desiderati.</span><span class="sxs-lookup"><span data-stu-id="b7275-142">The users assigned to this test should be configured with the desired voice policies.</span></span> <span data-ttu-id="b7275-143">I test estesi vengono quindi passati al cmdlet **New-CsWatcherNodeConfiguration** usando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b7275-143">The extended tests are then passed to the **New-CsWatcherNodeConfiguration** cmdlet by using a command similar to the following:</span></span>

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

<span data-ttu-id="b7275-144">Se New-CsWatcherNodeConfiguration viene chiamato senza usare il parametro tests, significa che solo le transazioni sintetiche predefinite (e la transazione sintetica estesa specificata) verranno abilitate per il nuovo nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="b7275-144">If New-CsWatcherNodeConfiguration is called without using the Tests parameter, that means that only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="b7275-145">Questo significa che il nodo Watcher testerà i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b7275-145">This means that the watcher node will test the following components:</span></span>

  - <span data-ttu-id="b7275-146">Registrazione</span><span class="sxs-lookup"><span data-stu-id="b7275-146">Registration</span></span>

  - <span data-ttu-id="b7275-147">Messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="b7275-147">IM</span></span>

  - <span data-ttu-id="b7275-148">GroupIM</span><span class="sxs-lookup"><span data-stu-id="b7275-148">GroupIM</span></span>

  - <span data-ttu-id="b7275-149">P2PAV (sessioni audio/video peer-to-peer)</span><span class="sxs-lookup"><span data-stu-id="b7275-149">P2PAV (peer-to-peer audio/video sessions)</span></span>

  - <span data-ttu-id="b7275-150">AvConference (audio/servizi di conferenza)</span><span class="sxs-lookup"><span data-stu-id="b7275-150">AvConference (audio/conferencing)</span></span>

  - <span data-ttu-id="b7275-151">Icone di presenza</span><span class="sxs-lookup"><span data-stu-id="b7275-151">Presence</span></span>

  - <span data-ttu-id="b7275-152">ABS (servizio Rubrica)</span><span class="sxs-lookup"><span data-stu-id="b7275-152">ABS (Address Book service)</span></span>

  - <span data-ttu-id="b7275-153">ABWQ (servizio Web Rubrica)</span><span class="sxs-lookup"><span data-stu-id="b7275-153">ABWQ (Address Book web service)</span></span>

  - <span data-ttu-id="b7275-154">PSTN (chiamate gateway PSTN, specificate come test esteso.</span><span class="sxs-lookup"><span data-stu-id="b7275-154">PSTN (PSTN gateway calls, specified as an extended test.</span></span> <span data-ttu-id="b7275-155">Per impostazione predefinita, PSTN è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="b7275-155">By default, PSTN is disabled.</span></span> <span data-ttu-id="b7275-156">Il test è abilitato in questo caso solo perché il comando ha abilitato la rete PSTN usando il parametro ExtendedTests.</span><span class="sxs-lookup"><span data-stu-id="b7275-156">The test is enabled in this case only because the command enabled PSTN by using the ExtendedTests parameter.)</span></span>

<span data-ttu-id="b7275-157">Ciò significa anche che i componenti seguenti non verranno testati per impostazione predefinita:</span><span class="sxs-lookup"><span data-stu-id="b7275-157">This also means that the following components will not be tested by default:</span></span>

  - <span data-ttu-id="b7275-158">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="b7275-158">AVEdgeConnectivity</span></span>

  - <span data-ttu-id="b7275-159">MCXP2PIM (dispositivo mobile Instant Messaging)</span><span class="sxs-lookup"><span data-stu-id="b7275-159">MCXP2PIM (mobile device instant messaging)</span></span>

  - <span data-ttu-id="b7275-160">ExumConnectivity (messaggistica unificata di Exchange)</span><span class="sxs-lookup"><span data-stu-id="b7275-160">ExumConnectivity (Exchange Unified Messaging)</span></span>

  - <span data-ttu-id="b7275-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="b7275-161">JoinLauncher</span></span>

  - <span data-ttu-id="b7275-162">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="b7275-162">PersistentChatMessage</span></span>

  - <span data-ttu-id="b7275-163">Dataconference</span><span class="sxs-lookup"><span data-stu-id="b7275-163">DataConference</span></span>

  - <span data-ttu-id="b7275-164">XmppIM</span><span class="sxs-lookup"><span data-stu-id="b7275-164">XmppIM</span></span>

  - <span data-ttu-id="b7275-165">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="b7275-165">UnifiedContactStore</span></span>

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="b7275-166">Aggiunta e rimozione di transazioni sintetiche</span><span class="sxs-lookup"><span data-stu-id="b7275-166">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="b7275-167">Dopo aver configurato un nodo Watcher, è possibile usare il cmdlet **set-CsWatcherNodeConfiguration** per aggiungere o rimuovere transazioni sintetiche dal nodo.</span><span class="sxs-lookup"><span data-stu-id="b7275-167">After a watcher node has been configured, you can use the **Set-CsWatcherNodeConfiguration** cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="b7275-168">Ad esempio, per aggiungere il test PersistentChatMessage al nodo Watcher, usa il metodo Add e un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b7275-168">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

<span data-ttu-id="b7275-169">È possibile aggiungere più test separando i nomi dei test usando le virgole.</span><span class="sxs-lookup"><span data-stu-id="b7275-169">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="b7275-170">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b7275-170">For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

<span data-ttu-id="b7275-171">Si noti che si verificherà un errore se uno o più di questi test, ad esempio dataconference, sono già stati abilitati nel nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="b7275-171">Note that an error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="b7275-172">In questo caso, viene visualizzato un messaggio di errore simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b7275-172">In this case, you will receive an error message similar to the following:</span></span>

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

<span data-ttu-id="b7275-173">Quando si verifica questo errore, non verrà applicata alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="b7275-173">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="b7275-174">Il comando deve essere ripetuto con il test duplicato rimosso.</span><span class="sxs-lookup"><span data-stu-id="b7275-174">The command should be rerun with the duplicate test removed.</span></span>

<span data-ttu-id="b7275-175">Per rimuovere una transazione sintetica da un nodo Watcher, usa il metodo Remove invece del metodo Add.</span><span class="sxs-lookup"><span data-stu-id="b7275-175">To remove a synthetic transaction from a watcher node, use the Remove method instead of the Add method.</span></span> <span data-ttu-id="b7275-176">Ad esempio, questo comando rimuove il test ABWQ da un nodo Watcher:</span><span class="sxs-lookup"><span data-stu-id="b7275-176">For example, this command removes the ABWQ test from a watcher node:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

<span data-ttu-id="b7275-177">Puoi anche usare il metodo Replace per sostituire tutti i test attualmente abilitati con uno o più nuovi test.</span><span class="sxs-lookup"><span data-stu-id="b7275-177">You can also use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="b7275-178">Ad esempio, se si vuole che un nodo Watcher esegua il test di messaggistica istantanea, è possibile configurarlo usando questo comando:</span><span class="sxs-lookup"><span data-stu-id="b7275-178">For example, if you only want a watcher node to run the IM test, you can configure that by using this command:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

<span data-ttu-id="b7275-179">Quando si esegue il comando precedente, tutte le transazioni sintetiche del nodo Watcher specificato verranno disabilitate ad eccezione di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="b7275-179">When you run the preceding command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="b7275-180">Visualizzazione e test della configurazione dei nodi Watcher</span><span class="sxs-lookup"><span data-stu-id="b7275-180">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="b7275-181">Se si vogliono visualizzare i test assegnati a un nodo Watcher, usare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="b7275-181">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

<span data-ttu-id="b7275-182">Il comando precedente restituirà informazioni simili a queste, a seconda delle transazioni sintetiche assegnate al nodo:</span><span class="sxs-lookup"><span data-stu-id="b7275-182">The preceding command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>

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
> <span data-ttu-id="b7275-183">Per visualizzare le transazioni sintetiche in ordine alfabetico, USA invece questo comando:</span><span class="sxs-lookup"><span data-stu-id="b7275-183">To view the synthetic transactions in alphabetical order, use this command instead:</span></span><BR><span data-ttu-id="b7275-184">Get-CsWatcherNodeConfiguration – Identity "atl-cs-001.litwareinc.com" | Select-Object-test ExpandProperty | Oggetto ordinamento</span><span class="sxs-lookup"><span data-stu-id="b7275-184">Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object</span></span>



</div>

<span data-ttu-id="b7275-185">Per verificare che sia stato creato un nodo Watcher, digitare il comando seguente all'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="b7275-185">To verify that a watcher node has been created, type the following command from within the Lync Server Management Shell:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="b7275-186">Verranno ricevute informazioni simili a queste:</span><span class="sxs-lookup"><span data-stu-id="b7275-186">You will receive information similar to this:</span></span>

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

<span data-ttu-id="b7275-187">Per verificare che il nodo Watcher sia stato configurato correttamente, digitare il comando seguente all'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="b7275-187">To verify that the watcher node has been configured correctly, type the following command from within the Lync Server Management Shell:</span></span>

    Test-CsWatcherNodeConfiguration

<span data-ttu-id="b7275-188">Il comando precedente testerà ogni nodo Watcher nella distribuzione e fornirà informazioni, ad esempio se:</span><span class="sxs-lookup"><span data-stu-id="b7275-188">The preceding command will test each watcher node in your deployment and tell you information, such as whether:</span></span>

  - <span data-ttu-id="b7275-189">Il ruolo di registrar richiesto è stato installato.</span><span class="sxs-lookup"><span data-stu-id="b7275-189">The required Registrar role been installed.</span></span>

  - <span data-ttu-id="b7275-190">La chiave del registro di sistema necessaria è stata creata per l'utente quando è stato eseguito set-CsWatcherNodeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="b7275-190">The required registry key was created for you when you ran Set-CsWatcherNodeConfiguration.</span></span>

  - <span data-ttu-id="b7275-191">I server stanno usando la versione corretta di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b7275-191">Your servers are running the correct version of Lync Server.</span></span>

  - <span data-ttu-id="b7275-192">Le porte sono state configurate correttamente.</span><span class="sxs-lookup"><span data-stu-id="b7275-192">Your ports been configured correctly.</span></span>

  - <span data-ttu-id="b7275-193">Gli utenti di test assegnati hanno le credenziali necessarie.</span><span class="sxs-lookup"><span data-stu-id="b7275-193">Your assigned test users have the required credentials.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

