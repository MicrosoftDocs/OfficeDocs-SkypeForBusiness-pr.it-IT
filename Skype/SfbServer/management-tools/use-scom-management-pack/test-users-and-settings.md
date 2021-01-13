---
title: Configurare gli utenti e le impostazioni per il test del nodo Watcher
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: 'Riepilogo: configurare gli account utente di test e le impostazioni dei nodi Watcher per le transazioni sintetiche di Skype for Business Server.'
ms.openlocfilehash: 687aec65089939d2f4cb7b110b4139eca28433fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814836"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="d91fa-103">Configurare gli utenti e le impostazioni per il test del nodo Watcher</span><span class="sxs-lookup"><span data-stu-id="d91fa-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="d91fa-104">**Riepilogo:** Configurare gli account utente di test e le impostazioni dei nodi Watcher per le transazioni sintetiche di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d91fa-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="d91fa-105">Dopo avere configurato il computer che fungerà da nodo Watcher, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d91fa-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="d91fa-106">[Configurare gli account utente di test](test-users-and-settings.md#testuser) per l'utilizzo da parte di questi nodi Watcher.</span><span class="sxs-lookup"><span data-stu-id="d91fa-106">[Configure Test User Accounts](test-users-and-settings.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="d91fa-107">Se si utilizza il metodo di autenticazione Negotiate, è inoltre necessario utilizzare il cmdlet **Set-CsTestUserCredential** per abilitare questi account di test per l'utilizzo nel nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="d91fa-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="d91fa-108">Aggiornare le impostazioni di configurazione del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="d91fa-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="d91fa-109">Configurare gli account utente di test</span><span class="sxs-lookup"><span data-stu-id="d91fa-109">Configure Test User Accounts</span></span>
<span data-ttu-id="d91fa-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="d91fa-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="d91fa-111">Gli account di test non devono rappresentare persone effettive, ma devono essere account di Active Directory validi.</span><span class="sxs-lookup"><span data-stu-id="d91fa-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="d91fa-112">Inoltre, questi account devono essere abilitati per Skype for Business Server, devono disporre di indirizzi SIP validi e devono essere abilitati per VoIP aziendale (per utilizzare la transazione sintetica Test-CsPstnPeerToPeerCall).</span><span class="sxs-lookup"><span data-stu-id="d91fa-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="d91fa-113">Se si utilizza il metodo di autenticazione TrustedServer, è necessario fare in modo che questi account esistano e configurarli come indicato.</span><span class="sxs-lookup"><span data-stu-id="d91fa-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="d91fa-114">È consigliabile assegnare almeno due utenti di test per ogni pool che si desidera testare.</span><span class="sxs-lookup"><span data-stu-id="d91fa-114">You should assign at least two test users for each pool that you want to test.</span></span> <span data-ttu-id="d91fa-115">Se si utilizza il metodo di autenticazione Negotiate, è necessario utilizzare anche il cmdlet Set-CsTestUserCredential e Skype for Business Server Management Shell per consentire l'utilizzo di tali account con le transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="d91fa-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="d91fa-116">A tale scopo, eseguire un comando simile al seguente (questi comandi presumono che siano stati creati i due account utente di Active Directory e che questi account siano abilitati per Skype for Business Server):</span><span class="sxs-lookup"><span data-stu-id="d91fa-116">Do this by running a command similar to the following (these commands assume that the two Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

<span data-ttu-id="d91fa-117">È necessario includere non solo l'indirizzo SIP, ma anche il nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="d91fa-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="d91fa-118">Se non si include la password, il cmdlet Set-CsTestUserCredential richiederà di immettere tali informazioni.</span><span class="sxs-lookup"><span data-stu-id="d91fa-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="d91fa-119">Il nome utente può essere specificato utilizzando il formato del nome di dominio profili\nome visualizzato nel blocco di codice precedente.</span><span class="sxs-lookup"><span data-stu-id="d91fa-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="d91fa-120">Per verificare che le credenziali dell'utente di test siano state create, eseguire questi comandi da Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="d91fa-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

<span data-ttu-id="d91fa-121">Per ogni utente verranno restituite informazioni simili a quelle seguenti:</span><span class="sxs-lookup"><span data-stu-id="d91fa-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="d91fa-122">**UserName**</span><span class="sxs-lookup"><span data-stu-id="d91fa-122">**UserName**</span></span>|<span data-ttu-id="d91fa-123">**Password**</span><span class="sxs-lookup"><span data-stu-id="d91fa-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d91fa-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="d91fa-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="d91fa-125">System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="d91fa-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="d91fa-126">Configurare un nodo Watcher di base con le transazioni sintetiche predefinite</span><span class="sxs-lookup"><span data-stu-id="d91fa-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="d91fa-127">Dopo aver creato gli utenti di test, è possibile creare un nodo Watcher utilizzando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d91fa-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

<span data-ttu-id="d91fa-128">Questo comando crea un nuovo nodo Watcher che utilizza le impostazioni predefinite ed esegue il set predefinito di transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="d91fa-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="d91fa-129">Il nuovo nodo Watcher utilizza anche gli utenti di test watcher1@litwareinc.com e watcher2@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="d91fa-129">The new watcher node also uses the test users watcher1@litwareinc.com, and watcher2@litwareinc.com.</span></span> <span data-ttu-id="d91fa-130">Se il nodo Watcher utilizza l'autenticazione di TrustedServer, i due account di test possono essere tutti gli account utente validi abilitati per Active Directory e Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d91fa-130">If the watcher node uses TrustedServer authentication, the two test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="d91fa-131">Se il nodo Watcher utilizza il metodo di autenticazione Negotiate, questi account utente devono essere abilitati anche per il nodo Watcher utilizzando il cmdlet Set-CsTestUserCredential.</span><span class="sxs-lookup"><span data-stu-id="d91fa-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="d91fa-132">Per convalidare che l'individuazione automatica del pool di destinazione per l'accesso è configurata correttamente anziché indirizzare un pool direttamente, utilizzare invece questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="d91fa-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="d91fa-133">Configurazione dei test estesi</span><span class="sxs-lookup"><span data-stu-id="d91fa-133">Configuring Extended Tests</span></span>

<span data-ttu-id="d91fa-134">Se si desidera abilitare il test PSTN, che verifica la connettività con la rete telefonica pubblica commutata, è necessario eseguire una configurazione aggiuntiva quando si configura il nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="d91fa-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="d91fa-135">Per prima cosa, è necessario associare gli utenti di test al tipo di test PSTN eseguendo un comando simile a questo da Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="d91fa-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="d91fa-136">I risultati di questo comando devono essere archiviati in una variabile.</span><span class="sxs-lookup"><span data-stu-id="d91fa-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="d91fa-137">In questo esempio, la variabile è denominata $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="d91fa-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="d91fa-138">Successivamente, è possibile utilizzare il cmdlet **New-CsWatcherNodeConfiguration** per associare il tipo di test (memorizzato nella variabile $pstnTest) a un pool di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d91fa-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="d91fa-139">Ad esempio, il comando seguente crea una nuova configurazione del nodo Watcher per il pool atl-cs-001.litwareinc.com, aggiungendo i due utenti di test creati in precedenza e aggiungendo il tipo di test PSTN:</span><span class="sxs-lookup"><span data-stu-id="d91fa-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the two test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="d91fa-140">Il comando precedente avrà esito negativo se non sono stati installati i file principali di Skype for Business Server e il database di RTCLocal nel computer del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="d91fa-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="d91fa-141">Per testare più criteri vocali, è possibile creare un test esteso per ogni criterio utilizzando il cmdlet **New-CsExtendedTest** .</span><span class="sxs-lookup"><span data-stu-id="d91fa-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="d91fa-142">Gli utenti forniti devono essere configurati con i criteri vocali desiderati.</span><span class="sxs-lookup"><span data-stu-id="d91fa-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="d91fa-143">I test estesi vengono passati al cmdlet **New-CsWatcherNodeConfiguration** utilizzando delimitatori virgola, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d91fa-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="d91fa-144">-ExtendedTests @ {Add = $pstnTest 1, $pstnTest 2, $pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="d91fa-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="d91fa-145">Poiché il cmdlet **New-CsWatcherNodeConfiguration** è stato chiamato senza utilizzare il parametro tests, verranno abilitate solo le transazioni sintetiche predefinite (e la transazione sintetica estesa specificata) per il nuovo nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="d91fa-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="d91fa-146">Di conseguenza, il nodo Watcher verificherà i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d91fa-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="d91fa-147">Registrazione</span><span class="sxs-lookup"><span data-stu-id="d91fa-147">Registration</span></span>
    
- <span data-ttu-id="d91fa-148">IM</span><span class="sxs-lookup"><span data-stu-id="d91fa-148">IM</span></span>
    
- <span data-ttu-id="d91fa-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="d91fa-149">GroupIM</span></span>
    
- <span data-ttu-id="d91fa-150">P2PAV (Sessioni audio/video peer-to-peer)</span><span class="sxs-lookup"><span data-stu-id="d91fa-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="d91fa-151">AvConference (Conferenze audio)</span><span class="sxs-lookup"><span data-stu-id="d91fa-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="d91fa-152">Presenza</span><span class="sxs-lookup"><span data-stu-id="d91fa-152">Presence</span></span>
    
- <span data-ttu-id="d91fa-153">ABS (Servizio Rubrica)</span><span class="sxs-lookup"><span data-stu-id="d91fa-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="d91fa-154">ABWQ (Servizio Web Rubrica)</span><span class="sxs-lookup"><span data-stu-id="d91fa-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="d91fa-155">Per impostazione predefinita, i componenti seguenti non verranno testati:</span><span class="sxs-lookup"><span data-stu-id="d91fa-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="d91fa-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="d91fa-156">ASConference</span></span>
    
- <span data-ttu-id="d91fa-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="d91fa-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="d91fa-158">Dataconference</span><span class="sxs-lookup"><span data-stu-id="d91fa-158">DataConference</span></span>
    
- <span data-ttu-id="d91fa-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="d91fa-159">DialinConferencing</span></span>
    
- <span data-ttu-id="d91fa-160">ExumConnectivity (Messaggistica unificata di Exchange)</span><span class="sxs-lookup"><span data-stu-id="d91fa-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="d91fa-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="d91fa-161">JoinLauncher</span></span>
    
- <span data-ttu-id="d91fa-162">MCXP2PIM (messaggistica istantanea del dispositivo mobile legacy)</span><span class="sxs-lookup"><span data-stu-id="d91fa-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="d91fa-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="d91fa-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="d91fa-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="d91fa-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="d91fa-165">PSTN (chiamate del gateway PSTN, specificate come test esteso)</span><span class="sxs-lookup"><span data-stu-id="d91fa-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="d91fa-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="d91fa-166">UcwaConference</span></span>
    
- <span data-ttu-id="d91fa-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="d91fa-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="d91fa-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="d91fa-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="d91fa-169">Aggiunta e rimozione di transazioni sintetiche</span><span class="sxs-lookup"><span data-stu-id="d91fa-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="d91fa-170">Dopo avere configurato un nodo Watcher, è possibile utilizzare il cmdlet Set-CsWatcherNodeConfiguration per aggiungere o rimuovere transazioni sintetiche dal nodo.</span><span class="sxs-lookup"><span data-stu-id="d91fa-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="d91fa-171">Ad esempio, per aggiungere il test PersistentChatMessage al nodo Watcher, utilizzare il metodo Add e un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d91fa-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="d91fa-172">È possibile aggiungere più test separandone i nomi con le virgole.</span><span class="sxs-lookup"><span data-stu-id="d91fa-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="d91fa-173">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d91fa-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="d91fa-174">Si verificherà un errore se uno o più di questi test (ad esempio, dataconference) sono già stati abilitati nel nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="d91fa-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="d91fa-175">In questo caso verrà visualizzato un messaggio di errore simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d91fa-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="d91fa-176">Set-CsWatcherNodeConfiguration: è presente una sequenza di tasti ' dataconference ' duplicata per il vincolo ' urn: schema: Microsoft. Rtc. Management. Settings. WatcherNode. 2010: TestName ' o l'identità univoca.</span><span class="sxs-lookup"><span data-stu-id="d91fa-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="d91fa-177">Quando si verifica questo errore, non vengono apportate modifiche.</span><span class="sxs-lookup"><span data-stu-id="d91fa-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="d91fa-178">Il comando deve essere eseguito di nuovo con il test duplicato rimosso.</span><span class="sxs-lookup"><span data-stu-id="d91fa-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="d91fa-179">Per rimuovere una transazione sintetica da un nodo Watcher, utilizzare il metodo Remove.</span><span class="sxs-lookup"><span data-stu-id="d91fa-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="d91fa-180">Ad esempio, questo comando rimuove il test ABWQ da un nodo Watcher:</span><span class="sxs-lookup"><span data-stu-id="d91fa-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="d91fa-181">È possibile utilizzare il metodo Replace per sostituire tutti i test attualmente abilitati con uno o più nuovi test.</span><span class="sxs-lookup"><span data-stu-id="d91fa-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="d91fa-182">Ad esempio, se si desidera che un nodo Watcher esegua solo il test di messaggistica istantanea, è possibile configurarlo utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d91fa-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="d91fa-183">Quando si esegue questo comando, tutte le transazioni sintetiche sul nodo Watcher specificato verranno disabilitate tranne che per la messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="d91fa-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="d91fa-184">Visualizzazione e verifica della configurazione del nodo Watcher</span><span class="sxs-lookup"><span data-stu-id="d91fa-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="d91fa-185">Se si desidera visualizzare i test assegnati a un nodo Watcher, utilizzare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d91fa-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="d91fa-186">Questo comando restituirà informazioni simili a quelle, a seconda delle transazioni sintetiche che sono state assegnate al nodo:</span><span class="sxs-lookup"><span data-stu-id="d91fa-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="d91fa-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage dataconference</span><span class="sxs-lookup"><span data-stu-id="d91fa-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="d91fa-188">Per visualizzare le transazioni sintetiche in ordine alfabetico, utilizzare invece il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d91fa-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="d91fa-189">Per verificare che sia stato creato un nodo Watcher, digitare il comando seguente da Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="d91fa-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="d91fa-190">Verranno restituite informazioni simili alle seguenti:</span><span class="sxs-lookup"><span data-stu-id="d91fa-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="d91fa-191">Identità: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d91fa-191">Identity : atl-cs-001.litwareinc.com</span></span> <br/>
<span data-ttu-id="d91fa-192">TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...}</span><span class="sxs-lookup"><span data-stu-id="d91fa-192">TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span><br/>
<span data-ttu-id="d91fa-193">ExtendedTests: {TestUsers = IList<System. String>; Name = test PSTN; Te...}</span><span class="sxs-lookup"><span data-stu-id="d91fa-193">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span><br/>
<span data-ttu-id="d91fa-194">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d91fa-194">TargetFqdn : atl-cs-001.litwareinc.com</span></span><br/>
<span data-ttu-id="d91fa-195">NumeroPorta: 5061</span><span class="sxs-lookup"><span data-stu-id="d91fa-195">PortNumber : 5061</span></span><br/>

<span data-ttu-id="d91fa-196">Per verificare che il nodo Watcher sia stato configurato correttamente, digitare il comando seguente da Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="d91fa-196">To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="d91fa-197">Questo comando consente di testare ogni nodo Watcher nella distribuzione e di verificare se sono state completate le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d91fa-197">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="d91fa-198">Viene installato il ruolo di registrazione obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="d91fa-198">The required Registrar role is installed.</span></span>
    
- <span data-ttu-id="d91fa-199">Viene creata la chiave del registro di sistema obbligatoria (completata quando è stato eseguito il cmdlet Set-CsWatcherNodeConfiguration).</span><span class="sxs-lookup"><span data-stu-id="d91fa-199">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet).</span></span>
    
- <span data-ttu-id="d91fa-200">I server eseguono la versione corretta di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d91fa-200">Your servers are running the correct version of Skype for Business Server.</span></span>
    
- <span data-ttu-id="d91fa-201">Le porte sono configurate correttamente.</span><span class="sxs-lookup"><span data-stu-id="d91fa-201">Your ports are configured correctly.</span></span>
    
- <span data-ttu-id="d91fa-202">Gli utenti di test assegnati dispongono delle credenziali necessarie.</span><span class="sxs-lookup"><span data-stu-id="d91fa-202">Your assigned test users have the required credentials.</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="d91fa-203">Gestione dei nodi Watcher</span><span class="sxs-lookup"><span data-stu-id="d91fa-203">Managing Watcher Nodes</span></span>
<span data-ttu-id="d91fa-204"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="d91fa-204"><a name="testuser"> </a></span></span>

<span data-ttu-id="d91fa-205">Oltre a modificare le transazioni sintetiche eseguite su un nodo Watcher, è anche possibile utilizzare il cmdlet **set-CsWatcherNodeConfiguration** per eseguire altre due attività importanti: abilitazione e disabilitazione del nodo Watcher e configurazione del nodo Watcher per l'utilizzo di URL Web interni o URL Web esterni durante l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="d91fa-205">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="d91fa-206">Per impostazione predefinita, i nodi Watcher sono progettati per eseguire periodicamente tutte le transazioni sintetiche abilitate.</span><span class="sxs-lookup"><span data-stu-id="d91fa-206">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="d91fa-207">A volte, tuttavia, potrebbe essere necessario sospendere tali transazioni.</span><span class="sxs-lookup"><span data-stu-id="d91fa-207">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="d91fa-208">Se il nodo Watcher è temporaneamente disconnesso dalla rete, ad esempio, non vi è alcun motivo per eseguire le transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="d91fa-208">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="d91fa-209">Senza la connettività di rete, tali transazioni avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="d91fa-209">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="d91fa-210">Per disabilitare temporaneamente un nodo Watcher, eseguire un comando simile a questo da Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="d91fa-210">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="d91fa-211">Questo comando consente di disabilitare l'esecuzione delle transazioni sintetiche sul nodo Watcher ATL watcher 001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="d91fa-211">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="d91fa-212">Per riprendere l'esecuzione delle transazioni sintetiche, reimpostare la proprietà Enabled su True ($True):</span><span class="sxs-lookup"><span data-stu-id="d91fa-212">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="d91fa-213">È possibile utilizzare la proprietà Enabled per attivare o disattivare i nodi Watcher.</span><span class="sxs-lookup"><span data-stu-id="d91fa-213">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="d91fa-214">Per eliminare in modo definitivo un nodo Watcher, utilizzare il cmdlet **Remove-CsWatcherNodeConfiguration**:</span><span class="sxs-lookup"><span data-stu-id="d91fa-214">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="d91fa-215">Questo comando rimuove tutte le impostazioni di configurazione del nodo Watcher dal computer specificato, in modo da evitare che il computer esegua automaticamente transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="d91fa-215">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="d91fa-216">Tuttavia, il comando non disinstalla i file dell'agente centrale di sistema o i file di sistema di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d91fa-216">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="d91fa-217">Per impostazione predefinita, i nodi Watcher utilizzano gli URL Web esterni di un'organizzazione durante la gestione dei test.</span><span class="sxs-lookup"><span data-stu-id="d91fa-217">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="d91fa-218">Tuttavia, i nodi Watcher possono anche essere configurati per l'utilizzo degli URL Web interni dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d91fa-218">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="d91fa-219">Ciò consente agli amministratori di verificare l'accesso agli URL per gli utenti che si trovano all'interno della rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="d91fa-219">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="d91fa-220">Per configurare un nodo Watcher per l'utilizzo di URL interni anziché di URL esterni, impostare la proprietà UseInternalWebURls su true ($True):</span><span class="sxs-lookup"><span data-stu-id="d91fa-220">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="d91fa-221">La reimpostazione di questa proprietà sul valore predefinito false ($False) provocherà nuovamente l'utilizzo degli URL esterni da parte di Watcher:</span><span class="sxs-lookup"><span data-stu-id="d91fa-221">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="d91fa-222">Istruzioni di configurazione speciali per le transazioni sintetiche</span><span class="sxs-lookup"><span data-stu-id="d91fa-222">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="d91fa-223"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="d91fa-223"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="d91fa-224">La maggior parte delle transazioni sintetiche può essere eseguita in un nodo Watcher così com'è.</span><span class="sxs-lookup"><span data-stu-id="d91fa-224">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="d91fa-225">Nella maggior parte dei casi, non appena viene aggiunta la transazione sintetica alle impostazioni di configurazione del nodo Watcher, il nodo Watcher può iniziare a utilizzare tale transazione sintetica durante le sessioni di test.</span><span class="sxs-lookup"><span data-stu-id="d91fa-225">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="d91fa-226">Tuttavia, esistono alcune transazioni sintetiche che richiedono istruzioni di installazione speciali, come descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="d91fa-226">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="d91fa-227">Transazioni sintetiche di conferenza dati</span><span class="sxs-lookup"><span data-stu-id="d91fa-227">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="d91fa-228">Se il computer del nodo Watcher si trova all'esterno della rete perimetrale, è probabile che non sia possibile eseguire la transazione sintetica di conferenza dati a meno che non sia stato prima disabilitato le impostazioni del proxy del browser Internet di Windows Internet® Explorer per l'account di servizio di rete, eseguendo la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="d91fa-228">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="d91fa-229">Nel computer del nodo Watcher fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Accessori**, fare clic con il pulsante destro del mouse su **prompt dei comandi** e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="d91fa-229">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="d91fa-230">Nella finestra della console digitare il comando seguente e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="d91fa-230">In the console window, type the following command and then press ENTER.</span></span> 
    
    ```console
    bitsadmin /util /SetIEProxy NetworkService NO_PROXY
    ```

    <span data-ttu-id="d91fa-231">Nella finestra di comando verrà visualizzato il messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="d91fa-231">You will see the following message displayed in the command window:</span></span>

    ```console
    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
  
    Internet proxy settings for account NetworkService set to NO_PROXY. 
      
    (connection = default)
    ```
      
    <span data-ttu-id="d91fa-232">Questo messaggio indica che sono state disabilitate le impostazioni del proxy di Internet Explorer per l'account di servizio di rete.</span><span class="sxs-lookup"><span data-stu-id="d91fa-232">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="d91fa-233">Transazione sintetica di messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="d91fa-233">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="d91fa-234">La transazione sintetica di messaggistica unificata di Exchange verifica che gli utenti di test siano in grado di connettersi agli account della segreteria telefonica ospitati in Exchange.</span><span class="sxs-lookup"><span data-stu-id="d91fa-234">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="d91fa-235">Gli utenti di test dovranno essere preconfigurati con gli account della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="d91fa-235">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="d91fa-236">Transazioni sintetiche di chat persistente</span><span class="sxs-lookup"><span data-stu-id="d91fa-236">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="d91fa-237">Per utilizzare la transazione sintetica per la chat persistente, è necessario innanzitutto creare un canale e fornire le autorizzazioni agli utenti di test per utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="d91fa-237">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="d91fa-238">È possibile utilizzare la transazione sintetica Persistent Chat per configurare questo canale:</span><span class="sxs-lookup"><span data-stu-id="d91fa-238">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```powershell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="d91fa-239">È necessario eseguire questa operazione di installazione deve essere eseguita dall'interno dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="d91fa-239">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="d91fa-240">Se si esegue da un computer non server, l'utente che esegue il cmdlet deve essere un membro del ruolo CsPersistentChatAdministrators per il controllo di accesso Role-Based (RBAC).</span><span class="sxs-lookup"><span data-stu-id="d91fa-240">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="d91fa-241">Se viene eseguito dal server stesso, l'utente che esegue il cmdlet deve essere un membro del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d91fa-241">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="d91fa-242">Transazione sintetica delle chiamate peer-to-peer PSTN</span><span class="sxs-lookup"><span data-stu-id="d91fa-242">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="d91fa-243">La transazione sintetica Test-CsPstnPeerToPeerCall verifica la possibilità di effettuare e ricevere chiamate tramite una rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="d91fa-243">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="d91fa-244">Per eseguire questa transazione sintetica, è necessario configurare:</span><span class="sxs-lookup"><span data-stu-id="d91fa-244">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="d91fa-245">Due utenti di test abilitati per le comunicazioni unificate (un chiamante e un destinatario).</span><span class="sxs-lookup"><span data-stu-id="d91fa-245">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="d91fa-246">Numeri DID (Direct Inward Dialing) per ogni account utente.</span><span class="sxs-lookup"><span data-stu-id="d91fa-246">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="d91fa-247">Criteri VoIP e route vocali che consentono alle chiamate al numero del destinatario di raggiungere il gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="d91fa-247">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="d91fa-248">Un gateway PSTN che accetta la chiamata e il supporto che instraderà le chiamate al pool di casa del destinatario, in base al numero composto.</span><span class="sxs-lookup"><span data-stu-id="d91fa-248">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="d91fa-249">Transazioni sintetiche dell'archivio contatti unificato</span><span class="sxs-lookup"><span data-stu-id="d91fa-249">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="d91fa-250">La transazione sintetica archivio contatti unificato verifica la capacità di Skype for Business Server di recuperare i contatti per conto di un utente da Exchange.</span><span class="sxs-lookup"><span data-stu-id="d91fa-250">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="d91fa-251">Per utilizzare questa transazione sintetica, devono essere soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d91fa-251">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="d91fa-252">Lyss-Exchange l'autenticazione da server a server deve essere configurata.</span><span class="sxs-lookup"><span data-stu-id="d91fa-252">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="d91fa-253">Gli utenti di test devono disporre di una cassetta postale di Exchange valida.</span><span class="sxs-lookup"><span data-stu-id="d91fa-253">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="d91fa-254">Dopo aver soddisfatto queste condizioni, è possibile eseguire il seguente cmdlet di Windows PowerShell per eseguire la migrazione degli elenchi di contatti degli utenti di test a Exchange:</span><span class="sxs-lookup"><span data-stu-id="d91fa-254">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="d91fa-255">Potrebbe essere necessario un po' di tempo prima che gli elenchi dei contatti degli utenti di test vengano migrati in Exchange.</span><span class="sxs-lookup"><span data-stu-id="d91fa-255">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="d91fa-256">Per monitorare lo stato di avanzamento della migrazione, è possibile eseguire la stessa riga di comando senza il flag-Setup:</span><span class="sxs-lookup"><span data-stu-id="d91fa-256">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="d91fa-257">Questa riga di comando avrà esito positivo dopo il completamento della migrazione.</span><span class="sxs-lookup"><span data-stu-id="d91fa-257">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="d91fa-258">Transazione sintetica XMPP</span><span class="sxs-lookup"><span data-stu-id="d91fa-258">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="d91fa-259">La transazione sintetica per la messaggistica istantanea con protocollo XMPP (Extensible Messaging and Presence Protocol) richiede che la caratteristica XMPP venga configurata con uno o più domini federati.</span><span class="sxs-lookup"><span data-stu-id="d91fa-259">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="d91fa-260">Per abilitare la transazione sintetica XMPP, è necessario fornire un parametro XmppTestReceiverMailAddress con un account utente in un dominio XMPP instradabile.</span><span class="sxs-lookup"><span data-stu-id="d91fa-260">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="d91fa-261">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="d91fa-261">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="d91fa-262">In questo esempio, deve esistere una regola di Skype for Business Server per instradare i messaggi per litwareinc.com a un gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="d91fa-262">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="d91fa-263">I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015 ma non sono più supportati in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d91fa-263">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="d91fa-264">Per ulteriori informazioni, vedere [migrazione della Federazione XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="d91fa-264">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="d91fa-265">Transazione sintetica video Interop Server (VIS)</span><span class="sxs-lookup"><span data-stu-id="d91fa-265">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="d91fa-266">La transazione sintetica video Interop Server (VIS) richiede il download e l'installazione dei file di supporto per le transazioni sintetiche ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span><span class="sxs-lookup"><span data-stu-id="d91fa-266">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="d91fa-267">Per installare VISSTSupportPackage.msi assicurarsi che le dipendenze (in requisiti di sistema) per il MSI siano già installate.</span><span class="sxs-lookup"><span data-stu-id="d91fa-267">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="d91fa-268">Eseguire VISSTSupportPackage.msi per eseguire un'installazione semplice.</span><span class="sxs-lookup"><span data-stu-id="d91fa-268">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="d91fa-269">Con estensione msi vengono installati tutti i file nel percorso seguente: "pacchetto di supporto per le transazioni sintetiche di%ProgramFiles%\VIS".</span><span class="sxs-lookup"><span data-stu-id="d91fa-269">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="d91fa-270">Per ulteriori informazioni su come eseguire la transazione sintetica VIS, fare riferimento alla documentazione relativa al cmdlet [test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) .</span><span class="sxs-lookup"><span data-stu-id="d91fa-270">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="d91fa-271">Modifica della frequenza di esecuzione per le transazioni sintetiche</span><span class="sxs-lookup"><span data-stu-id="d91fa-271">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="d91fa-272"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="d91fa-272"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="d91fa-273">Per impostazione predefinita, le transazioni sintetiche verranno eseguite con gli utenti configurati ogni 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="d91fa-273">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="d91fa-274">Le transazioni sintetiche vengono eseguite sequenzialmente all'interno di un set di utenti per evitare che due transazioni sintetiche entrino in conflitto tra loro.</span><span class="sxs-lookup"><span data-stu-id="d91fa-274">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="d91fa-275">Un intervallo più lungo è necessario per garantire il completamento di tutte le transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="d91fa-275">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="d91fa-276">Se si desidera eseguire più frequentemente transazioni sintetiche, è necessario ridurre il numero di transazioni sintetiche eseguite con un determinato gruppo di utenti, in modo che i test possano essere completati nell'intervallo di tempo desiderato con alcuni buffer per i ritardi di rete occasionali.</span><span class="sxs-lookup"><span data-stu-id="d91fa-276">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="d91fa-277">Se è consigliabile eseguire più transazioni sintetiche, creare più set di utenti per l'esecuzione di ulteriori transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="d91fa-277">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="d91fa-278">Per modificare la frequenza di esecuzione delle transazioni sintetiche, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="d91fa-278">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="d91fa-279">Aprire System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="d91fa-279">Open System Center Operations Manager.</span></span> <span data-ttu-id="d91fa-280">Fare clic su sezione Creazione e modifica.</span><span class="sxs-lookup"><span data-stu-id="d91fa-280">Click Authoring section.</span></span> <span data-ttu-id="d91fa-281">Fare clic su regole sezione (in creazione e modifica).</span><span class="sxs-lookup"><span data-stu-id="d91fa-281">Click Rules section (under Authoring).</span></span>
    
2. <span data-ttu-id="d91fa-282">Nella sezione regole individuare la regola con il nome "regola di raccolta delle prestazioni del Runner di transazioni sintetiche principale".</span><span class="sxs-lookup"><span data-stu-id="d91fa-282">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule".</span></span>
    
3. <span data-ttu-id="d91fa-283">Fare clic con il pulsante destro del mouse sulla regola e selezionare sostituzioni, selezionare Sostituisci la regola e quindi selezionare "per tutti gli oggetti della classe: Watcher del pool".</span><span class="sxs-lookup"><span data-stu-id="d91fa-283">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher".</span></span>
    
4. <span data-ttu-id="d91fa-284">Nella finestra proprietà di sostituzione selezionare il nome del parametro "Frequency" e impostare il valore di sostituzione su quello desiderato.</span><span class="sxs-lookup"><span data-stu-id="d91fa-284">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="d91fa-285">Nella stessa finestra selezionare il Management Pack a cui deve essere applicata la sostituzione.</span><span class="sxs-lookup"><span data-stu-id="d91fa-285">In the same window, select the Management pack to which this override needs to be applied.</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="d91fa-286">Utilizzo della registrazione dettagliata per le transazioni sintetiche</span><span class="sxs-lookup"><span data-stu-id="d91fa-286">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="d91fa-287"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="d91fa-287"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="d91fa-288">Le transazioni sintetiche risultano estremamente utili per identificare i problemi del sistema.</span><span class="sxs-lookup"><span data-stu-id="d91fa-288">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="d91fa-289">Ad esempio, il cmdlet Test-CsRegistration possibile avvisare gli amministratori del fatto che gli utenti hanno avuto difficoltà a registrarsi con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d91fa-289">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="d91fa-290">Tuttavia, potrebbero essere necessari ulteriori dettagli per determinare la causa effettiva di un errore.</span><span class="sxs-lookup"><span data-stu-id="d91fa-290">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="d91fa-291">Per questo motivo, le transazioni sintetiche offrono una registrazione avanzata.</span><span class="sxs-lookup"><span data-stu-id="d91fa-291">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="d91fa-292">Con una registrazione completa, per ogni attività eseguita da una transazione sintetica, vengono registrate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d91fa-292">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="d91fa-293">L'ora di inizio dell'attività.</span><span class="sxs-lookup"><span data-stu-id="d91fa-293">The time that the activity started.</span></span>
    
- <span data-ttu-id="d91fa-294">Data e ora di fine dell'attività.</span><span class="sxs-lookup"><span data-stu-id="d91fa-294">The time that the activity finished.</span></span>
    
- <span data-ttu-id="d91fa-295">Azione eseguita, ad esempio la creazione, l'aggiunta o l'uscita di una conferenza, l'accesso a Skype for Business Server, l'invio di un messaggio istantaneo.</span><span class="sxs-lookup"><span data-stu-id="d91fa-295">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="d91fa-296">Messaggi informativi, dettagliati, di avviso o di errore generati durante l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="d91fa-296">Informational, verbose, warning, or error messages generated when the activity ran.</span></span>
    
- <span data-ttu-id="d91fa-297">Messaggi di registrazione SIP.</span><span class="sxs-lookup"><span data-stu-id="d91fa-297">SIP registration messages.</span></span>
    
- <span data-ttu-id="d91fa-298">Record di eccezioni o codici diagnostici generati durante l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="d91fa-298">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="d91fa-299">Risultato netto dell'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="d91fa-299">The net result of running the activity.</span></span>
    
<span data-ttu-id="d91fa-300">Queste informazioni vengono generate automaticamente ogni volta che viene eseguita una transazione sintetica, ma non vengono visualizzate o salvate automaticamente in un file di registro.</span><span class="sxs-lookup"><span data-stu-id="d91fa-300">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="d91fa-301">Se si esegue manualmente una transazione sintetica, è possibile utilizzare il parametro OutLoggerVariable per specificare una variabile di Windows PowerShell in cui verranno archiviate le informazioni.</span><span class="sxs-lookup"><span data-stu-id="d91fa-301">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="d91fa-302">Da qui, è possibile utilizzare uno dei due metodi per salvare e/o visualizzare i messaggi di errore nel log RTF in formato XML o HTML.</span><span class="sxs-lookup"><span data-stu-id="d91fa-302">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="d91fa-303">Per recuperare le informazioni sulla risoluzione dei problemi, specificare il parametro OutLoggerVariable, seguito da un nome di variabile che si sceglie:</span><span class="sxs-lookup"><span data-stu-id="d91fa-303">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="d91fa-304">Non anteporre il carattere $ al nome di variabile.</span><span class="sxs-lookup"><span data-stu-id="d91fa-304">Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="d91fa-305">Utilizzare un nome di variabile, ad esempio RegistrationTest (non $RegistrationTest).</span><span class="sxs-lookup"><span data-stu-id="d91fa-305">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="d91fa-306">Quando si esegue questo comando, viene visualizzato un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d91fa-306">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="d91fa-307">FQDN di destinazione: atl-cs-001.litwareinc.com result: latenza errore: 00:00:00 messaggio di errore: questo computer non dispone di alcun certificato assegnato.</span><span class="sxs-lookup"><span data-stu-id="d91fa-307">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="d91fa-308">Diagnosi: è possibile accedere a informazioni molto più dettagliate per questo errore rispetto al messaggio di errore riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d91fa-308">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span>

<span data-ttu-id="d91fa-309">Per accedere a queste informazioni in formato HTML, utilizzare un comando simile al seguente per salvare le informazioni archiviate nella variabile RegistrationTest in un file HTML:</span><span class="sxs-lookup"><span data-stu-id="d91fa-309">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="d91fa-310">In alternativa, è possibile usare il metodo ToXML() per salvare i dati in un file XML:</span><span class="sxs-lookup"><span data-stu-id="d91fa-310">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="d91fa-311">È possibile visualizzare questi file utilizzando Windows Internet Explorer, Microsoft Visual Studio o qualsiasi altra applicazione in grado di aprire file HTML/XML.</span><span class="sxs-lookup"><span data-stu-id="d91fa-311">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="d91fa-312">Le transazioni sintetiche eseguite dall'interno di System Center Operations Manager genereranno automaticamente questi file di registro per gli errori.</span><span class="sxs-lookup"><span data-stu-id="d91fa-312">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="d91fa-313">Questi registri non verranno generati se l'esecuzione ha esito negativo prima che Skype for Business Server PowerShell sia in grado di caricare ed eseguire la transazione sintetica.</span><span class="sxs-lookup"><span data-stu-id="d91fa-313">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="d91fa-314">Per impostazione predefinita, in Skype for Business Server i file di registro vengono salvati in una cartella non condivisa.</span><span class="sxs-lookup"><span data-stu-id="d91fa-314">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="d91fa-315">Per rendere tali registri facilmente accessibili, è necessario condividere questa cartella.</span><span class="sxs-lookup"><span data-stu-id="d91fa-315">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="d91fa-316">Ad esempio: \\ ATL-watcher-001. litwareinc. com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="d91fa-316">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
