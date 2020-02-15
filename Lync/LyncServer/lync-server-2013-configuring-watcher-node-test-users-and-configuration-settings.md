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

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="c8184-102">Configurazione degli utenti e delle impostazioni di configurazione del nodo Watcher in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8184-102">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8184-103">_**Ultimo argomento modificato:** 2013-07-29_</span><span class="sxs-lookup"><span data-stu-id="c8184-103">_**Topic Last Modified:** 2013-07-29_</span></span>

<span data-ttu-id="c8184-104">Dopo avere configurato il computer che fungerà da nodo Watcher, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8184-104">After configuring the computer that will act as a watcher node, you must:</span></span>

1.  <span data-ttu-id="c8184-105">Creare gli account di test che devono essere utilizzati da questi nodi Watcher.</span><span class="sxs-lookup"><span data-stu-id="c8184-105">Create the test accounts to be used by these watcher nodes.</span></span> <span data-ttu-id="c8184-106">Se si utilizza il metodo di autenticazione Negotiate, è inoltre necessario utilizzare il cmdlet [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) per abilitare questi account di test per l'utilizzo nel nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="c8184-106">If you are using the Negotiate authentication method, you must also use the [Set-CsTestUserCredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) cmdlet to enable these test accounts for use on the watcher node.</span></span>

2.  <span data-ttu-id="c8184-107">Aggiornare le impostazioni di configurazione del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="c8184-107">Update the watcher node configuration settings.</span></span>

<span data-ttu-id="c8184-108">In questa sezione vengono trattati i temi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8184-108">This section covers:</span></span>

  - <span data-ttu-id="c8184-109">Configurazione degli account utente di test</span><span class="sxs-lookup"><span data-stu-id="c8184-109">Configuring Test User Accounts</span></span>

  - <span data-ttu-id="c8184-110">Configurazione di un nodo Watcher di base con le transazioni sintetiche predefinite</span><span class="sxs-lookup"><span data-stu-id="c8184-110">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

  - <span data-ttu-id="c8184-111">Configurazione dei test estesi</span><span class="sxs-lookup"><span data-stu-id="c8184-111">Configuring Extended Tests</span></span>

  - <span data-ttu-id="c8184-112">Aggiunta e rimozione di transazioni sintetiche</span><span class="sxs-lookup"><span data-stu-id="c8184-112">Adding and Removing Synthetic Transactions</span></span>

  - <span data-ttu-id="c8184-113">Visualizzazione e verifica della configurazione del nodo Watcher</span><span class="sxs-lookup"><span data-stu-id="c8184-113">Viewing and Testing the Watcher Node Configuration</span></span>

<div>

## <a name="configuring-test-user-accounts"></a><span data-ttu-id="c8184-114">Configurazione degli account utente di test</span><span class="sxs-lookup"><span data-stu-id="c8184-114">Configuring Test User Accounts</span></span>

<span data-ttu-id="c8184-115">Gli utenti di test non devono rappresentare persone effettive, ma devono essere account di servizi di dominio Active Directory validi; Inoltre, questi account devono essere abilitati per Lync Server 2013, devono disporre di indirizzi SIP validi e devono essere abilitati per VoIP aziendale (per utilizzare la transazione sintetica Test-CsPstnPeerToPeerCall).</span><span class="sxs-lookup"><span data-stu-id="c8184-115">Test users do not need to represent actual people, but they must be valid Active Directory Domain Services accounts; in addition, these accounts must be enabled for Lync Server 2013, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> <span data-ttu-id="c8184-116">Se si utilizza il metodo di autenticazione TrustedServer, è necessario fare in modo che questi account esistano e siano stati configurati come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="c8184-116">If you use the TrustedServer authentication method, then all you need to do is to make sure that these accounts exist and have been configured as specified here.</span></span> <span data-ttu-id="c8184-117">È consigliabile assegnare almeno tre utenti di test per ogni pool che si desidera testare.</span><span class="sxs-lookup"><span data-stu-id="c8184-117">You should assign at least three test users for each pool that you want to test.</span></span>

<span data-ttu-id="c8184-118">Se si utilizza il metodo di autenticazione Negotiate, è necessario utilizzare anche il cmdlet **Set-CsTestUserCredential** e Lync Server Management Shell per consentire l'utilizzo di tali account con le transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="c8184-118">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet and the Lync Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="c8184-119">A tale scopo, è possibile eseguire un comando simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="c8184-119">You can do this by running a command similar to the following.</span></span> <span data-ttu-id="c8184-120">(Questi comandi presumono che i tre account utente di Active Directory siano già stati creati e che tali account siano stati abilitati per Lync Server 2013):</span><span class="sxs-lookup"><span data-stu-id="c8184-120">(These commands assume that the three Active Directory user accounts have already been created and that those accounts have been enabled for Lync Server 2013.):</span></span>

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

<span data-ttu-id="c8184-121">Tenere presente che è necessario includere non solo l'indirizzo SIP, ma anche il nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="c8184-121">Note that you must include not only the SIP address but also the user name and password.</span></span> <span data-ttu-id="c8184-122">Se non si include la password Set-CsTestUserCredential verrà chiesto di immettere tali informazioni.</span><span class="sxs-lookup"><span data-stu-id="c8184-122">If you do not include the password Set-CsTestUserCredential will prompt you to enter that information.</span></span> <span data-ttu-id="c8184-123">Il nome utente può essere specificato utilizzando il formato nome\\utente di dominio visualizzato in alto oppure utilizzando il formato utente name@domain nome; Per esempio:</span><span class="sxs-lookup"><span data-stu-id="c8184-123">The user name can be specified using the domain name\\user name format shown above, or by using the format user name@domain name; for example:</span></span>

    -UserName "watcher3@litwareinc.com"

<span data-ttu-id="c8184-124">Per verificare che le credenziali dell'utente di test siano state create, eseguire questi comandi dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="c8184-124">To verify that the test user credentials were created, run these commands from within the Lync Server Management Shell:</span></span>

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

<span data-ttu-id="c8184-125">Per ogni utente verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8184-125">Information similar to this should be returned for each user:</span></span>

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="c8184-126">Configurazione di un nodo Watcher di base con le transazioni sintetiche predefinite</span><span class="sxs-lookup"><span data-stu-id="c8184-126">Configuring a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="c8184-127">Dopo avere creato gli utenti di test, è possibile creare un nodo Watcher utilizzando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c8184-127">After the test users have been created you can then create a watcher node by using a command similar to this:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

<span data-ttu-id="c8184-128">Questo comando crea un nuovo nodo Watcher che utilizza le impostazioni predefinite ed esegue il set predefinito di transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="c8184-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="c8184-129">Il nuovo nodo Watcher inoltre utilizza gli utenti di test watcher1@litwareinc.com, watcher2@litwareinc.com e watcher3@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="c8184-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="c8184-130">Se il nodo Watcher utilizza l'autenticazione di TrustedServer, i tre account di test possono essere tutti gli account utente validi abilitati per Active Directory e Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c8184-130">If the watcher node is using TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Lync Server.</span></span> <span data-ttu-id="c8184-131">Se il nodo Watcher utilizza il metodo di autenticazione Negotiate, è inoltre necessario abilitare tali account utente per il nodo Watcher mediante il cmdlet **Set-CsTestUserCredential**.</span><span class="sxs-lookup"><span data-stu-id="c8184-131">If the watcher node is using the Negotiate authentication method, you must also enable these user accounts for watcher node by using the **Set-CsTestUserCredential** cmdlet.</span></span>

</div>

<div>

## <a name="configuring-extended-tests"></a><span data-ttu-id="c8184-132">Configurazione dei test estesi</span><span class="sxs-lookup"><span data-stu-id="c8184-132">Configuring Extended Tests</span></span>

<span data-ttu-id="c8184-133">Se si desidera abilitare il test PSTN, che verifica la connettività alla rete PSTN (Public Switched Telephone Network), sarà necessario eseguire alcune attività di configurazione aggiuntive durante l'impostazione del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="c8184-133">If you want to enable the public switched telephone network (PSTN test), which verifies connectivity with the public switched telephone network, you will need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="c8184-134">È innanzitutto necessario associare gli utenti di test al tipo di test PSTN.</span><span class="sxs-lookup"><span data-stu-id="c8184-134">First, you need to associate your test users with the PSTN test type.</span></span> <span data-ttu-id="c8184-135">A tale scopo, eseguire un comando simile al seguente dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="c8184-135">To do that, run a command similar to this from within the Lync Server Management Shell:</span></span>

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

<span data-ttu-id="c8184-136">I risultati di questo comando devono essere archiviati in una variabile.</span><span class="sxs-lookup"><span data-stu-id="c8184-136">Note that the results of this command must be stored in a variable.</span></span> <span data-ttu-id="c8184-137">In questo esempio la variabile è denominata $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="c8184-137">In this example, that's a variable named $pstnTest.</span></span>

<span data-ttu-id="c8184-138">A questo punto, è possibile utilizzare il cmdlet **New-CsWatcherNodeConfiguration** per associare il tipo di test (archiviato nella variabile $pstnTest) a un pool di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c8184-138">At this point, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Lync Server 2013 pool.</span></span> <span data-ttu-id="c8184-139">Il comando seguente ad esempio crea la configurazione di un nuovo nodo Watcher per il pool atl-cs-001.litwareinc.com, aggiungendo i tre utenti di test creati in precedenza e il tipo di test PSTN:</span><span class="sxs-lookup"><span data-stu-id="c8184-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users that were created previously, and also adding the PSTN test type:</span></span>

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

<span data-ttu-id="c8184-140">Si noti che il comando precedente avrà esito negativo se non sono stati installati i file di base di Lync Server e il database di RTCLocal nel computer del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="c8184-140">Note that the preceding command will fail if you have not installed the Lync Server core files and the RTCLocal database on the watcher node computer.</span></span>

<span data-ttu-id="c8184-141">Per testare più criteri vocali, è necessario creare un test esteso per ogni criterio utilizzando il cmdlet **New-CsExtendedTest**.</span><span class="sxs-lookup"><span data-stu-id="c8184-141">To test multiple voice policies, you need to create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="c8184-142">Gli utenti assegnati a questo test devono essere configurati con i criteri vocali desiderati.</span><span class="sxs-lookup"><span data-stu-id="c8184-142">The users assigned to this test should be configured with the desired voice policies.</span></span> <span data-ttu-id="c8184-143">I test estesi vengono quindi passati al cmdlet **New-CsWatcherNodeConfiguration** mediante un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c8184-143">The extended tests are then passed to the **New-CsWatcherNodeConfiguration** cmdlet by using a command similar to the following:</span></span>

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

<span data-ttu-id="c8184-p110">Se New-CsWatcherNodeConfiguration viene chiamato senza utilizzare il parametro Tests, solo le transazioni sintetiche predefinite e la transazione sintetica estesa specificata saranno abilitate per il nuovo nodo Watcher. Questo significa che il nodo Watcher testerà i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8184-p110">If New-CsWatcherNodeConfiguration is called without using the Tests parameter, that means that only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node. This means that the watcher node will test the following components:</span></span>

  - <span data-ttu-id="c8184-146">Registrazione</span><span class="sxs-lookup"><span data-stu-id="c8184-146">Registration</span></span>

  - <span data-ttu-id="c8184-147">IM</span><span class="sxs-lookup"><span data-stu-id="c8184-147">IM</span></span>

  - <span data-ttu-id="c8184-148">GroupIM</span><span class="sxs-lookup"><span data-stu-id="c8184-148">GroupIM</span></span>

  - <span data-ttu-id="c8184-149">P2PAV (Sessioni audio/video peer-to-peer)</span><span class="sxs-lookup"><span data-stu-id="c8184-149">P2PAV (peer-to-peer audio/video sessions)</span></span>

  - <span data-ttu-id="c8184-150">AvConference (Conferenze audio)</span><span class="sxs-lookup"><span data-stu-id="c8184-150">AvConference (audio/conferencing)</span></span>

  - <span data-ttu-id="c8184-151">Presenza</span><span class="sxs-lookup"><span data-stu-id="c8184-151">Presence</span></span>

  - <span data-ttu-id="c8184-152">ABS (Servizio Rubrica)</span><span class="sxs-lookup"><span data-stu-id="c8184-152">ABS (Address Book service)</span></span>

  - <span data-ttu-id="c8184-153">ABWQ (Servizio Web Rubrica)</span><span class="sxs-lookup"><span data-stu-id="c8184-153">ABWQ (Address Book web service)</span></span>

  - <span data-ttu-id="c8184-p111">PSTN (Chiamate di gateway PSTN, specificate come test esteso. Per impostazione predefinita, il test PSTN è disabilitato. Il test è abilitato in questo caso solo perché è stato abilitato dal comando mediante l'utilizzo del parametro ExtendedTests).</span><span class="sxs-lookup"><span data-stu-id="c8184-p111">PSTN (PSTN gateway calls, specified as an extended test. By default, PSTN is disabled. The test is enabled in this case only because the command enabled PSTN by using the ExtendedTests parameter.)</span></span>

<span data-ttu-id="c8184-157">Questo inoltre significa che, per impostazione predefinita, non verranno testati i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8184-157">This also means that the following components will not be tested by default:</span></span>

  - <span data-ttu-id="c8184-158">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="c8184-158">AVEdgeConnectivity</span></span>

  - <span data-ttu-id="c8184-159">MCXP2PIM (messaggistica istantanea dei dispositivi mobili)</span><span class="sxs-lookup"><span data-stu-id="c8184-159">MCXP2PIM (mobile device instant messaging)</span></span>

  - <span data-ttu-id="c8184-160">ExumConnectivity (Messaggistica unificata di Exchange)</span><span class="sxs-lookup"><span data-stu-id="c8184-160">ExumConnectivity (Exchange Unified Messaging)</span></span>

  - <span data-ttu-id="c8184-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="c8184-161">JoinLauncher</span></span>

  - <span data-ttu-id="c8184-162">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="c8184-162">PersistentChatMessage</span></span>

  - <span data-ttu-id="c8184-163">Dataconference</span><span class="sxs-lookup"><span data-stu-id="c8184-163">DataConference</span></span>

  - <span data-ttu-id="c8184-164">XmppIM</span><span class="sxs-lookup"><span data-stu-id="c8184-164">XmppIM</span></span>

  - <span data-ttu-id="c8184-165">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="c8184-165">UnifiedContactStore</span></span>

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="c8184-166">Aggiunta e rimozione di transazioni sintetiche</span><span class="sxs-lookup"><span data-stu-id="c8184-166">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="c8184-167">Dopo avere configurato un nodo Watcher, è possibile utilizzare il cmdlet **Set-CsWatcherNodeConfiguration** per aggiungere o rimuovere transazioni sintetiche dal nodo.</span><span class="sxs-lookup"><span data-stu-id="c8184-167">After a watcher node has been configured, you can use the **Set-CsWatcherNodeConfiguration** cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="c8184-168">Ad esempio, per aggiungere il test PersistentChatMessage al nodo Watcher, utilizzare il metodo Add e un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c8184-168">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

<span data-ttu-id="c8184-p113">È possibile aggiungere più test separandone i nomi con le virgole. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c8184-p113">Multiple tests can be added by separating the test names by using commas. For example:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

<span data-ttu-id="c8184-p114">Se uno o più di questi test, ad esempio DataConference, sono già stati abilitati per il nodo Watcher, si verificherà un errore. In questo caso verrà visualizzato un messaggio di errore simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c8184-p114">Note that an error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node. In this case, you will receive an error message similar to the following:</span></span>

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

<span data-ttu-id="c8184-173">Quando si verifica questo errore, non vengono apportate modifiche.</span><span class="sxs-lookup"><span data-stu-id="c8184-173">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="c8184-174">Il comando deve essere eseguito di nuovo dopo avere rimosso il test duplicato.</span><span class="sxs-lookup"><span data-stu-id="c8184-174">The command should be rerun with the duplicate test removed.</span></span>

<span data-ttu-id="c8184-p116">Per rimuovere una transazione sintetica da un nodo Watcher, utilizzare il metodo Remove anziché il metodo Add. Ad esempio, questo comando rimuove il test ABWQ da un nodo Watcher:</span><span class="sxs-lookup"><span data-stu-id="c8184-p116">To remove a synthetic transaction from a watcher node, use the Remove method instead of the Add method. For example, this command removes the ABWQ test from a watcher node:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

<span data-ttu-id="c8184-p117">È inoltre possibile utilizzare il metodo Replace per sostituire tutti i test attualmente abilitati con uno o più test nuovi. Ad esempio, se si desidera che un nodo Watcher esegua solo il test IM, è possibile configurare questa condizione utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c8184-p117">You can also use the Replace method to replace all the currently-enabled tests with one or more new tests. For example, if you only want a watcher node to run the IM test, you can configure that by using this command:</span></span>

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

<span data-ttu-id="c8184-179">Quando si esegue il comando precedente, per il nodo Watcher specificato verranno disabilitate tutte le transazioni sintetiche tranne IM.</span><span class="sxs-lookup"><span data-stu-id="c8184-179">When you run the preceding command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="c8184-180">Visualizzazione e verifica della configurazione del nodo Watcher</span><span class="sxs-lookup"><span data-stu-id="c8184-180">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="c8184-181">Se si desidera visualizzare i test assegnati a un nodo Watcher, utilizzare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c8184-181">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

<span data-ttu-id="c8184-182">Il comando precedente restituirà informazioni simili alle seguenti, a seconda delle transazioni sintetiche assegnate al nodo:</span><span class="sxs-lookup"><span data-stu-id="c8184-182">The preceding command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>

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
> <span data-ttu-id="c8184-183">Per visualizzare le transazioni sintetiche in ordine alfabetico, utilizzare invece il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c8184-183">To view the synthetic transactions in alphabetical order, use this command instead:</span></span><BR><span data-ttu-id="c8184-184">Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object</span><span class="sxs-lookup"><span data-stu-id="c8184-184">Get-CsWatcherNodeConfiguration –Identity "atl-cs-001.litwareinc.com" | Select-Object –ExpandProperty Tests | Sort-Object</span></span>



</div>

<span data-ttu-id="c8184-185">Per verificare che sia stato creato un nodo Watcher, digitare il comando seguente dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="c8184-185">To verify that a watcher node has been created, type the following command from within the Lync Server Management Shell:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="c8184-186">Verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8184-186">You will receive information similar to this:</span></span>

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

<span data-ttu-id="c8184-187">Per verificare che il nodo Watcher sia stato configurato correttamente, digitare il comando seguente dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="c8184-187">To verify that the watcher node has been configured correctly, type the following command from within the Lync Server Management Shell:</span></span>

    Test-CsWatcherNodeConfiguration

<span data-ttu-id="c8184-188">Il comando precedente verificherà ogni nodo Watcher nella distribuzione e restituirà informazioni che indicano se:</span><span class="sxs-lookup"><span data-stu-id="c8184-188">The preceding command will test each watcher node in your deployment and tell you information, such as whether:</span></span>

  - <span data-ttu-id="c8184-189">Il ruolo Funzione di registrazione necessario è stato installato.</span><span class="sxs-lookup"><span data-stu-id="c8184-189">The required Registrar role been installed.</span></span>

  - <span data-ttu-id="c8184-190">La chiave del Registro di sistema necessaria è stata creata automaticamente durante l'esecuzione di Set-CsWatcherNodeConfiguration.</span><span class="sxs-lookup"><span data-stu-id="c8184-190">The required registry key was created for you when you ran Set-CsWatcherNodeConfiguration.</span></span>

  - <span data-ttu-id="c8184-191">I server eseguono la versione corretta di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c8184-191">Your servers are running the correct version of Lync Server.</span></span>

  - <span data-ttu-id="c8184-192">Le porte sono state configurate correttamente.</span><span class="sxs-lookup"><span data-stu-id="c8184-192">Your ports been configured correctly.</span></span>

  - <span data-ttu-id="c8184-193">Gli utenti di test assegnati dispongono delle credenziali necessarie.</span><span class="sxs-lookup"><span data-stu-id="c8184-193">Your assigned test users have the required credentials.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

