---
title: Configurare gli utenti e le impostazioni di test del nodo Watcher
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Riepilogo: configurare gli account utente di test e le impostazioni dei nodi Watcher per le transazioni sintetiche di Skype for Business Server.'
ms.openlocfilehash: 2e365e2212cd2ade76d02c878891e1bbfcfdc433
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799656"
---
# <a name="configure-watcher-node-test-users-and-settings"></a><span data-ttu-id="873db-103">Configurare gli utenti e le impostazioni di test del nodo Watcher</span><span class="sxs-lookup"><span data-stu-id="873db-103">Configure watcher node test users and settings</span></span>
 
<span data-ttu-id="873db-104">**Riepilogo:** Configurare gli account utente di test e le impostazioni dei nodi Watcher per le transazioni sintetiche di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="873db-104">**Summary:** Configure test user accounts and watcher node settings for Skype for Business Server synthetic transactions.</span></span>
  
<span data-ttu-id="873db-105">Dopo aver configurato il computer che fungerà da nodo Watcher, è necessario:</span><span class="sxs-lookup"><span data-stu-id="873db-105">After configuring the computer that will act as a watcher node, you must:</span></span>
  
1. <span data-ttu-id="873db-106">[Configurare gli account utente di test](test-users-and-settings-2019.md#testuser) per l'utilizzo da questi nodi Watcher.</span><span class="sxs-lookup"><span data-stu-id="873db-106">[Configure Test User Accounts](test-users-and-settings-2019.md#testuser) to be used by these watcher nodes.</span></span> <span data-ttu-id="873db-107">Se si usa il metodo di autenticazione Negotiate, è necessario usare anche il cmdlet **Set-CsTestUserCredential** per abilitare questi account di test per l'uso nel nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="873db-107">If you are using the Negotiate authentication method, you must also use the **Set-CsTestUserCredential** cmdlet to enable these test accounts for use on the watcher node.</span></span>
    
2. <span data-ttu-id="873db-108">Aggiornare le impostazioni di configurazione dei nodi Watcher.</span><span class="sxs-lookup"><span data-stu-id="873db-108">Update the watcher node configuration settings.</span></span>
    
## <a name="configure-test-user-accounts"></a><span data-ttu-id="873db-109">Configurare gli account utente di test</span><span class="sxs-lookup"><span data-stu-id="873db-109">Configure Test User Accounts</span></span>
<span data-ttu-id="873db-110"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="873db-110"><a name="testuser"> </a></span></span>

<span data-ttu-id="873db-111">Gli account di test non devono rappresentare persone effettive, ma devono essere account di Active Directory validi.</span><span class="sxs-lookup"><span data-stu-id="873db-111">Test accounts do not need to represent actual people, but they must be valid Active Directory accounts.</span></span> <span data-ttu-id="873db-112">Inoltre, questi account devono essere abilitati per Skype for Business Server, devono avere indirizzi SIP validi e devono essere abilitati per Enterprise Voice (per usare la transazione sintetica Test-CsPstnPeerToPeerCall).</span><span class="sxs-lookup"><span data-stu-id="873db-112">In addition, these accounts must be enabled for Skype for Business Server, they must have valid SIP addresses, and they should be enabled for Enterprise Voice (to use the Test-CsPstnPeerToPeerCall synthetic transaction).</span></span> 
  
<span data-ttu-id="873db-113">Se usi il metodo di autenticazione TrustedServer, devi solo assicurarti che questi account esistano e configurarli come indicato.</span><span class="sxs-lookup"><span data-stu-id="873db-113">If you are using the TrustedServer authentication method, all you need to do is to make sure that these accounts exist and configure them as noted.</span></span> <span data-ttu-id="873db-114">È consigliabile assegnare almeno tre utenti di test per ogni pool che si vuole testare.</span><span class="sxs-lookup"><span data-stu-id="873db-114">You should assign at least three test users for each pool that you want to test.</span></span> <span data-ttu-id="873db-115">Se si usa il metodo di autenticazione Negotiate, è necessario usare anche il cmdlet Set-CsTestUserCredential e Skype for Business Server Management Shell per consentire agli account di test di lavorare con le transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="873db-115">If you are using the Negotiate authentication method, you must also use the Set-CsTestUserCredential cmdlet and the Skype for Business Server Management Shell to enable these test accounts to work with the synthetic transactions.</span></span> <span data-ttu-id="873db-116">Eseguire questa operazione eseguendo un comando simile al seguente (questi comandi presuppongono che siano stati creati i tre account utente di Active Directory e che questi account siano abilitati per Skype for Business Server):</span><span class="sxs-lookup"><span data-stu-id="873db-116">Do this by running a command similar to the following (these commands assume that the three Active Directory user accounts have been created and that these accounts are enabled for Skype for Business Server):</span></span>
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

<span data-ttu-id="873db-117">È necessario includere non solo l'indirizzo SIP, ma anche il nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="873db-117">You must include not only the SIP address, but also the user name and password.</span></span> <span data-ttu-id="873db-118">Se non si include la password, il cmdlet Set-CsTestUserCredential chiederà di immettere le informazioni.</span><span class="sxs-lookup"><span data-stu-id="873db-118">If you do not include the password, the Set-CsTestUserCredential cmdlet will prompt you to enter that information.</span></span> <span data-ttu-id="873db-119">Il nome utente può essere specificato usando il formato del nome del dominio profili\nome visualizzato nel blocco di codice precedente.</span><span class="sxs-lookup"><span data-stu-id="873db-119">The user name can be specified by using the domain name\user name format shown in the preceding code block.</span></span>
  
<span data-ttu-id="873db-120">Per verificare che le credenziali dell'utente di test siano state create, eseguire questi comandi da Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="873db-120">To verify that the test user credentials were created, run these commands from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

<span data-ttu-id="873db-121">Le informazioni simili a queste verranno restituite per ogni utente:</span><span class="sxs-lookup"><span data-stu-id="873db-121">Information similar to this will be returned for each user:</span></span>
  
|<span data-ttu-id="873db-122">**UserName**</span><span class="sxs-lookup"><span data-stu-id="873db-122">**UserName**</span></span>|<span data-ttu-id="873db-123">**Password**</span><span class="sxs-lookup"><span data-stu-id="873db-123">**Password**</span></span>|
|:-----|:-----|
|<span data-ttu-id="873db-124">Litwareinc\watcher1</span><span class="sxs-lookup"><span data-stu-id="873db-124">Litwareinc\watcher1</span></span>  <br/> |<span data-ttu-id="873db-125">System. Security. SecureString</span><span class="sxs-lookup"><span data-stu-id="873db-125">System.Security.SecureString</span></span>  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a><span data-ttu-id="873db-126">Configurare un nodo Watcher di base con le transazioni sintetiche predefinite</span><span class="sxs-lookup"><span data-stu-id="873db-126">Configure a Basic Watcher Node with the Default Synthetic Transactions</span></span>

<span data-ttu-id="873db-127">Dopo aver creato gli utenti di test, è possibile creare un nodo Watcher usando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="873db-127">After the test users have been created, you can create a watcher node by using a command similar to this:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

<span data-ttu-id="873db-128">Questo comando crea un nuovo nodo Watcher che usa le impostazioni predefinite ed esegue il set predefinito di transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="873db-128">This command creates a new watcher node that uses the default settings and runs the default set of synthetic transactions.</span></span> <span data-ttu-id="873db-129">Il nuovo nodo Watcher usa anche gli utenti di test watcher1@litwareinc.com, watcher2@litwareinc.com e watcher3@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="873db-129">The new watcher node also uses the test users watcher1@litwareinc.com, watcher2@litwareinc.com, and watcher3@litwareinc.com.</span></span> <span data-ttu-id="873db-130">Se il nodo Watcher usa l'autenticazione TrustedServer, i tre account di test possono essere tutti gli account utente validi abilitati per Active Directory e Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="873db-130">If the watcher node uses TrustedServer authentication, the three test accounts can be any valid user accounts enabled for Active Directory and Skype for Business Server.</span></span> <span data-ttu-id="873db-131">Se il nodo Watcher usa il metodo di autenticazione Negotiate, questi account utente devono essere abilitati anche per il nodo Watcher usando il cmdlet Set-CsTestUserCredential.</span><span class="sxs-lookup"><span data-stu-id="873db-131">If the watcher node uses the Negotiate authentication method, these user accounts must also be enabled for the watcher node by using the Set-CsTestUserCredential cmdlet.</span></span>
  
<span data-ttu-id="873db-132">Per verificare che l'individuazione automatica del pool di destinazione per l'accesso sia configurata correttamente invece che come destinazione di un pool, usare direttamente questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="873db-132">To validate that automatic discovery of target pool to sign-in is configured correctly rather than targeting a pool directly use these steps instead:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a><span data-ttu-id="873db-133">Configurazione di test estesi</span><span class="sxs-lookup"><span data-stu-id="873db-133">Configuring Extended Tests</span></span>

<span data-ttu-id="873db-134">Se si vuole abilitare il test PSTN, che verifica la connettività con la rete telefonica pubblica commutata, è necessario eseguire altre configurazioni quando si configura il nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="873db-134">If you want to enable the PSTN test, which verifies connectivity with the public switched telephone network, you need to do some additional configuration when setting up the watcher node.</span></span> <span data-ttu-id="873db-135">Prima di tutto, devi associare gli utenti di test al tipo di test PSTN eseguendo un comando simile a quello di Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="873db-135">First, you must associate your test users with the PSTN test type by running a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> <span data-ttu-id="873db-136">I risultati di questo comando devono essere archiviati in una variabile.</span><span class="sxs-lookup"><span data-stu-id="873db-136">The results of this command must be stored in a variable.</span></span> <span data-ttu-id="873db-137">In questo esempio la variabile è denominata $pstnTest.</span><span class="sxs-lookup"><span data-stu-id="873db-137">In this example, the variable is named $pstnTest.</span></span> 
  
<span data-ttu-id="873db-138">Puoi quindi usare il cmdlet **New-CsWatcherNodeConfiguration** per associare il tipo di test (archiviato nella variabile $pstnTest) a un pool di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="873db-138">Next, you can use the **New-CsWatcherNodeConfiguration** cmdlet to associate the test type (stored in the variable $pstnTest) to a Skype for Business Server pool.</span></span> <span data-ttu-id="873db-139">Ad esempio, il comando seguente crea una nuova configurazione di nodi Watcher per il pool atl-cs-001.litwareinc.com, aggiungendo i tre utenti di test creati in precedenza e aggiungendo il tipo di test PSTN:</span><span class="sxs-lookup"><span data-stu-id="873db-139">For example, the following command creates a new watcher node configuration for the pool atl-cs-001.litwareinc.com, adding the three test users created previously, and adding the PSTN test type:</span></span>
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

<span data-ttu-id="873db-140">Il comando precedente non riesce se non sono stati installati i file principali di Skype for Business Server e il database di RTCLocal nel computer del nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="873db-140">The preceding command will fail if you have not installed the Skype for Business Server core files and the RTCLocal database on the watcher node computer.</span></span> 
  
<span data-ttu-id="873db-141">Per testare più criteri vocali, è possibile creare un test esteso per ogni criterio usando il cmdlet **New-CsExtendedTest** .</span><span class="sxs-lookup"><span data-stu-id="873db-141">To test multiple voice policies, you can create an extended test for each policy by using the **New-CsExtendedTest** cmdlet.</span></span> <span data-ttu-id="873db-142">Gli utenti forniti devono essere configurati con i criteri vocali desiderati.</span><span class="sxs-lookup"><span data-stu-id="873db-142">The users provided should be configured with the desired voice policies.</span></span> <span data-ttu-id="873db-143">I test estesi vengono passati al cmdlet **New-CsWatcherNodeConfiguration** usando i delimitatori virgola, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="873db-143">The extended tests are passed to the **New-CsWatcherNodeConfiguration** cmdlet by using comma-delimiters, such as:</span></span>
  
<span data-ttu-id="873db-144">-ExtendedTests @ {Add = $pstnTest 1, $pstnTest 2, $pstnTest 3}</span><span class="sxs-lookup"><span data-stu-id="873db-144">-ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}</span></span>
  
<span data-ttu-id="873db-145">Poiché il cmdlet **New-CsWatcherNodeConfiguration** è stato chiamato senza usare il parametro tests, verranno abilitate solo le transazioni sintetiche predefinite (e la transazione sintetica estesa specificata) per il nuovo nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="873db-145">Because the **New-CsWatcherNodeConfiguration** cmdlet was called without using the Tests parameter, only the Default synthetic transactions (and the specified extended synthetic transaction) will be enabled for the new watcher node.</span></span> <span data-ttu-id="873db-146">Di conseguenza, il nodo Watcher testerà i componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="873db-146">Therefore, the watcher node will test the following components:</span></span>
  
- <span data-ttu-id="873db-147">Registrazione</span><span class="sxs-lookup"><span data-stu-id="873db-147">Registration</span></span>
    
- <span data-ttu-id="873db-148">Messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="873db-148">IM</span></span>
    
- <span data-ttu-id="873db-149">GroupIM</span><span class="sxs-lookup"><span data-stu-id="873db-149">GroupIM</span></span>
    
- <span data-ttu-id="873db-150">P2PAV (sessioni audio/video peer-to-peer)</span><span class="sxs-lookup"><span data-stu-id="873db-150">P2PAV (peer-to-peer audio/video sessions)</span></span>
    
- <span data-ttu-id="873db-151">AvConference (audio/servizi di conferenza)</span><span class="sxs-lookup"><span data-stu-id="873db-151">AvConference (audio/conferencing)</span></span>
    
- <span data-ttu-id="873db-152">Icone di presenza</span><span class="sxs-lookup"><span data-stu-id="873db-152">Presence</span></span>
    
- <span data-ttu-id="873db-153">ABS (servizio Rubrica)</span><span class="sxs-lookup"><span data-stu-id="873db-153">ABS (Address Book service)</span></span>
    
- <span data-ttu-id="873db-154">ABWQ (servizio Web Rubrica)</span><span class="sxs-lookup"><span data-stu-id="873db-154">ABWQ (Address Book web service)</span></span>
    
<span data-ttu-id="873db-155">I componenti seguenti non verranno testati per impostazione predefinita:</span><span class="sxs-lookup"><span data-stu-id="873db-155">The following components will not be tested by default:</span></span>
  
- <span data-ttu-id="873db-156">ASConference</span><span class="sxs-lookup"><span data-stu-id="873db-156">ASConference</span></span>
    
- <span data-ttu-id="873db-157">AVEdgeConnectivity</span><span class="sxs-lookup"><span data-stu-id="873db-157">AVEdgeConnectivity</span></span>
    
- <span data-ttu-id="873db-158">Dataconference</span><span class="sxs-lookup"><span data-stu-id="873db-158">DataConference</span></span>
    
- <span data-ttu-id="873db-159">DialinConferencing</span><span class="sxs-lookup"><span data-stu-id="873db-159">DialinConferencing</span></span>
    
- <span data-ttu-id="873db-160">ExumConnectivity (messaggistica unificata di Exchange)</span><span class="sxs-lookup"><span data-stu-id="873db-160">ExumConnectivity (Exchange Unified Messaging)</span></span>
    
- <span data-ttu-id="873db-161">JoinLauncher</span><span class="sxs-lookup"><span data-stu-id="873db-161">JoinLauncher</span></span>
    
- <span data-ttu-id="873db-162">MCXP2PIM (dispositivo mobile legacy Instant Messaging)</span><span class="sxs-lookup"><span data-stu-id="873db-162">MCXP2PIM (legacy mobile device instant messaging)</span></span>
    
- <span data-ttu-id="873db-163">P2PVideoInteropServerSipTrunkAV</span><span class="sxs-lookup"><span data-stu-id="873db-163">P2PVideoInteropServerSipTrunkAV</span></span>
    
- <span data-ttu-id="873db-164">PersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="873db-164">PersistentChatMessage</span></span>
    
- <span data-ttu-id="873db-165">PSTN (chiamate gateway PSTN, specificate come test esteso)</span><span class="sxs-lookup"><span data-stu-id="873db-165">PSTN (PSTN gateway calls, specified as an extended test)</span></span>
    
- <span data-ttu-id="873db-166">UcwaConference</span><span class="sxs-lookup"><span data-stu-id="873db-166">UcwaConference</span></span>
    
- <span data-ttu-id="873db-167">UnifiedContactStore</span><span class="sxs-lookup"><span data-stu-id="873db-167">UnifiedContactStore</span></span>
    
- <span data-ttu-id="873db-168">XmppIM</span><span class="sxs-lookup"><span data-stu-id="873db-168">XmppIM</span></span>
    
### <a name="adding-and-removing-synthetic-transactions"></a><span data-ttu-id="873db-169">Aggiunta e rimozione di transazioni sintetiche</span><span class="sxs-lookup"><span data-stu-id="873db-169">Adding and Removing Synthetic Transactions</span></span>

<span data-ttu-id="873db-170">Dopo aver configurato un nodo Watcher, è possibile usare il cmdlet Set-CsWatcherNodeConfiguration per aggiungere o rimuovere transazioni sintetiche dal nodo.</span><span class="sxs-lookup"><span data-stu-id="873db-170">After a watcher node has been configured, you can use the Set-CsWatcherNodeConfiguration cmdlet to add or remove synthetic transactions from the node.</span></span> <span data-ttu-id="873db-171">Ad esempio, per aggiungere il test PersistentChatMessage al nodo Watcher, usa il metodo Add e un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="873db-171">For example, to add the PersistentChatMessage test to the watcher node, use the Add method and a command similar to this:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

<span data-ttu-id="873db-172">È possibile aggiungere più test separando i nomi dei test usando le virgole.</span><span class="sxs-lookup"><span data-stu-id="873db-172">Multiple tests can be added by separating the test names by using commas.</span></span> <span data-ttu-id="873db-173">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="873db-173">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

<span data-ttu-id="873db-174">Si verificherà un errore se uno o più di questi test, ad esempio dataconference, sono già stati abilitati nel nodo Watcher.</span><span class="sxs-lookup"><span data-stu-id="873db-174">An error will occur if one or more of these tests (for example, DataConference) has already been enabled on the watcher node.</span></span> <span data-ttu-id="873db-175">In questo caso, viene visualizzato un messaggio di errore simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="873db-175">In this case, you will receive an error message similar to the following:</span></span>
  
<span data-ttu-id="873db-176">Set-CsWatcherNodeConfiguration: è presente una sequenza di tasti duplicata "dataconference" per la chiave "urn: schema: Microsoft. Rtc. Management. Settings. WatcherNode. 2010: TestName" o un vincolo di identità univoco.</span><span class="sxs-lookup"><span data-stu-id="873db-176">Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.</span></span>
  
<span data-ttu-id="873db-177">Quando si verifica questo errore, non verrà applicata alcuna modifica.</span><span class="sxs-lookup"><span data-stu-id="873db-177">When this error occurs, no changes will be applied.</span></span> <span data-ttu-id="873db-178">Il comando deve essere eseguito di nuovo con il test duplicato rimosso.</span><span class="sxs-lookup"><span data-stu-id="873db-178">The command should be re-run with the duplicate test removed.</span></span>
  
<span data-ttu-id="873db-179">Per rimuovere una transazione sintetica da un nodo Watcher, usa il metodo Remove.</span><span class="sxs-lookup"><span data-stu-id="873db-179">To remove a synthetic transaction from a watcher node, use the Remove method.</span></span> <span data-ttu-id="873db-180">Ad esempio, questo comando rimuove il test ABWQ da un nodo Watcher:</span><span class="sxs-lookup"><span data-stu-id="873db-180">For example, this command removes the ABWQ test from a watcher node:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

<span data-ttu-id="873db-181">Puoi usare il metodo Replace per sostituire tutti i test attualmente abilitati con uno o più nuovi test.</span><span class="sxs-lookup"><span data-stu-id="873db-181">You can use the Replace method to replace all the currently-enabled tests with one or more new tests.</span></span> <span data-ttu-id="873db-182">Ad esempio, se si vuole che un nodo Watcher esegua solo il test di messaggistica istantanea, è possibile configurarlo usando questo comando:</span><span class="sxs-lookup"><span data-stu-id="873db-182">For example, if you want a watcher node only to run the IM test, you can configure that by using this command:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

<span data-ttu-id="873db-183">Quando si esegue questo comando, tutte le transazioni sintetiche nel nodo Watcher specificato verranno disabilitate ad eccezione di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="873db-183">When you run this command, all synthetic transactions on the specified watcher node will be disabled except for IM.</span></span>
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a><span data-ttu-id="873db-184">Visualizzazione e test della configurazione dei nodi Watcher</span><span class="sxs-lookup"><span data-stu-id="873db-184">Viewing and Testing the Watcher Node Configuration</span></span>

<span data-ttu-id="873db-185">Se si vogliono visualizzare i test assegnati a un nodo Watcher, usare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="873db-185">If you want to view the tests that have been assigned to a watcher node, use a command similar to this:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

<span data-ttu-id="873db-186">Questo comando restituirà informazioni simili a queste, a seconda delle transazioni sintetiche assegnate al nodo:</span><span class="sxs-lookup"><span data-stu-id="873db-186">This command will return information similar to this, depending on the synthetic transactions that have been assigned to the node:</span></span>
  
<span data-ttu-id="873db-187">Registrazione IM GroupIM P2PAV AvConference presenza PersistentChatMessage dataconference</span><span class="sxs-lookup"><span data-stu-id="873db-187">Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference</span></span>
> [!TIP]
> <span data-ttu-id="873db-188">Per visualizzare le transazioni sintetiche in ordine alfabetico, USA invece questo comando:</span><span class="sxs-lookup"><span data-stu-id="873db-188">To view the synthetic transactions in alphabetical order, use this command instead:</span></span> 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

<span data-ttu-id="873db-189">Per verificare che sia stato creato un nodo Watcher, digitare il comando seguente da Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="873db-189">To verify that a watcher node has been created, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

<span data-ttu-id="873db-190">Le informazioni verranno restituite in modo simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="873db-190">You will get back information similar to this:</span></span>
  
<span data-ttu-id="873db-191">Identità: atl-cs-001.litwareinc.com TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com...}</span><span class="sxs-lookup"><span data-stu-id="873db-191">Identity : atl-cs-001.litwareinc.com TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}</span></span> <span data-ttu-id="873db-192">ExtendedTests: {TestUsers = IList<System. String>; Name = test PSTN; Te...}</span><span class="sxs-lookup"><span data-stu-id="873db-192">ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}</span></span> <span data-ttu-id="873db-193">TargetFqdn: atl-cs-001.litwareinc.com NumeroPorta: 5061To verificare che il nodo Watcher sia stato configurato correttamente, digitare il comando seguente da Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="873db-193">TargetFqdn : atl-cs-001.litwareinc.com PortNumber : 5061To verify that the watcher node has been configured correctly, type the following command from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

<span data-ttu-id="873db-194">Questo comando testerà ogni nodo Watcher nella distribuzione e confermerà se sono state completate le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="873db-194">This command will test each watcher node in your deployment and confirm whether the following actions are completed:</span></span>
  
- <span data-ttu-id="873db-195">Il ruolo di registrar richiesto è installato</span><span class="sxs-lookup"><span data-stu-id="873db-195">The required Registrar role is installed</span></span>
    
- <span data-ttu-id="873db-196">Viene creata la chiave del registro di sistema necessaria (completata quando è stato eseguito il cmdlet Set-CsWatcherNodeConfiguration)</span><span class="sxs-lookup"><span data-stu-id="873db-196">The required registry key is created (completed when you ran the Set-CsWatcherNodeConfiguration cmdlet)</span></span>
    
- <span data-ttu-id="873db-197">I server stanno usando la versione corretta di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="873db-197">Your servers are running the correct version of Skype for Business Server</span></span>
    
- <span data-ttu-id="873db-198">Le porte sono configurate correttamente</span><span class="sxs-lookup"><span data-stu-id="873db-198">Your ports are configured correctly</span></span>
    
- <span data-ttu-id="873db-199">Gli utenti di test assegnati hanno le credenziali necessarie</span><span class="sxs-lookup"><span data-stu-id="873db-199">Your assigned test users have the required credentials</span></span>
    
## <a name="managing-watcher-nodes"></a><span data-ttu-id="873db-200">Gestione dei nodi Watcher</span><span class="sxs-lookup"><span data-stu-id="873db-200">Managing Watcher Nodes</span></span>
<span data-ttu-id="873db-201"><a name="testuser"> </a></span><span class="sxs-lookup"><span data-stu-id="873db-201"><a name="testuser"> </a></span></span>

<span data-ttu-id="873db-202">Oltre a modificare le transazioni sintetiche eseguite in un nodo Watcher, puoi anche usare il cmdlet **set-CsWatcherNodeConfiguration** per eseguire due altre attività importanti: abilitare e disabilitare il nodo Watcher e configurare il nodo Watcher per usare URL Web interni o URL Web esterni durante l'esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="873db-202">In addition to modifying the synthetic transactions that are executed on a watcher node, you can also use the **Set-CsWatcherNodeConfiguration** cmdlet to carry out two other important tasks: enabling and disabling the watcher node, and configuring the watcher node to use either internal Web URLs or external Web URLs when running its tests.</span></span>
  
<span data-ttu-id="873db-203">Per impostazione predefinita, i nodi Watcher sono progettati per eseguire periodicamente tutte le transazioni sintetiche abilitate.</span><span class="sxs-lookup"><span data-stu-id="873db-203">By default, watcher nodes are designed to periodically run all their enabled synthetic transactions.</span></span> <span data-ttu-id="873db-204">A volte, tuttavia, potresti voler sospendere tali transazioni.</span><span class="sxs-lookup"><span data-stu-id="873db-204">At times, however, you may want to suspend those transactions.</span></span> <span data-ttu-id="873db-205">Ad esempio, se il nodo Watcher è temporaneamente disconnesso dalla rete, non c'è alcun motivo per eseguire le transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="873db-205">For example, if the watcher node is temporarily disconnected from the network, then there is no reason to run the synthetic transactions.</span></span> <span data-ttu-id="873db-206">Senza connettività di rete, le transazioni non riusciranno.</span><span class="sxs-lookup"><span data-stu-id="873db-206">Without network connectivity, those transactions will fail.</span></span> <span data-ttu-id="873db-207">Per disabilitare temporaneamente un nodo Watcher, eseguire un comando simile a questo da Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="873db-207">To temporarily disable a watcher node, run a command similar to this from the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

<span data-ttu-id="873db-208">Questo comando consente di disabilitare l'esecuzione di transazioni sintetiche nel nodo Watcher watcher 001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="873db-208">This command will disable the execution of synthetic transactions on the watcher node atl watcher 001.litwareinc.com.</span></span> <span data-ttu-id="873db-209">Per riprendere l'esecuzione delle transazioni sintetiche, impostare di nuovo la proprietà Enabled su true ($True):</span><span class="sxs-lookup"><span data-stu-id="873db-209">To resume execution of the synthetic transactions, set the Enabled property back to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> <span data-ttu-id="873db-210">La proprietà Enabled può essere usata per attivare o disattivare i nodi Watcher.</span><span class="sxs-lookup"><span data-stu-id="873db-210">The Enabled property can be used to turn watcher nodes on or off.</span></span> <span data-ttu-id="873db-211">Se si vuole eliminare definitivamente un nodo Watcher, usare il cmdlet **Remove-CsWatcherNodeConfiguration** :</span><span class="sxs-lookup"><span data-stu-id="873db-211">If you want to permanently delete a watcher node, use the **Remove-CsWatcherNodeConfiguration** cmdlet:</span></span>
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

<span data-ttu-id="873db-212">Questo comando rimuove tutte le impostazioni di configurazione del nodo Watcher dal computer specificato, impedendo che il computer esegua automaticamente le transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="873db-212">That command removes all the watcher node configuration settings from the specified computer, which prevents that computer from automatically running synthetic transactions.</span></span> <span data-ttu-id="873db-213">Tuttavia, il comando non disinstalla i file dell'agente del centro di sistema o i file di sistema di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="873db-213">However, the command does not uninstall the System Center agent files or the Skype for Business Server system files.</span></span>
  
<span data-ttu-id="873db-214">Per impostazione predefinita, i nodi Watcher usano gli URL Web esterni di un'organizzazione durante l'esecuzione di test.</span><span class="sxs-lookup"><span data-stu-id="873db-214">By default, watcher nodes use an organization's external Web URLs when conducting tests.</span></span> <span data-ttu-id="873db-215">Tuttavia, i nodi Watcher possono essere configurati anche per l'uso degli URL Web interni dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="873db-215">However, watcher nodes can also be configured to use the organization's internal Web URLs.</span></span> <span data-ttu-id="873db-216">Ciò consente agli amministratori di verificare l'accesso URL per gli utenti che si trovano all'interno della rete perimetrale.</span><span class="sxs-lookup"><span data-stu-id="873db-216">This enables administrators to verify URL access for users located inside the perimeter network.</span></span> <span data-ttu-id="873db-217">Per configurare un nodo Watcher per l'uso di URL interni anziché di URL esterni, imposta la proprietà UseInternalWebURls su true ($True):</span><span class="sxs-lookup"><span data-stu-id="873db-217">To configure a watcher node to use internal URLs instead of external URLs, set the UseInternalWebURls property to True ($True):</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

<span data-ttu-id="873db-218">La reimpostazione di questa proprietà sul valore predefinito false ($False) farà sì che il Watcher usi ancora una volta gli URL esterni:</span><span class="sxs-lookup"><span data-stu-id="873db-218">Resetting this property to the default value of False ($False) will cause the watcher to once again use the external URLs:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a><span data-ttu-id="873db-219">Istruzioni per la configurazione speciale per le transazioni sintetiche</span><span class="sxs-lookup"><span data-stu-id="873db-219">Special Setup Instructions for Synthetic Transactions</span></span>
<span data-ttu-id="873db-220"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="873db-220"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="873db-221">La maggior parte delle transazioni sintetiche può essere eseguita in un nodo Watcher così com'è.</span><span class="sxs-lookup"><span data-stu-id="873db-221">Most synthetic transactions can run on a watcher node as-is.</span></span> <span data-ttu-id="873db-222">Nella maggior parte dei casi, non appena viene aggiunta la transazione sintetica alle impostazioni di configurazione dei nodi Watcher, il nodo Watcher può iniziare a usare tale transazione sintetica durante le sessioni di test.</span><span class="sxs-lookup"><span data-stu-id="873db-222">In most cases, as soon as the synthetic transaction is added to the watcher node configuration settings, the watcher node can begin using that synthetic transaction during its test passes.</span></span> <span data-ttu-id="873db-223">Esistono tuttavia alcune transazioni sintetiche che richiedono istruzioni di configurazione speciali, come descritto nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="873db-223">However, there are some synthetic transactions that require special setup instructions, as discussed in the following sections.</span></span>
  
### <a name="data-conferencing-synthetic-transaction"></a><span data-ttu-id="873db-224">Transazione sintetica per i servizi di conferenza dati</span><span class="sxs-lookup"><span data-stu-id="873db-224">Data Conferencing Synthetic Transaction</span></span>

<span data-ttu-id="873db-225">Se il computer del nodo Watcher si trova all'esterno della rete perimetrale, probabilmente non sarà possibile eseguire la transazione sintetica per i servizi di conferenza dati a meno che non si disattivi prima di tutto Windows Internet Explorer® impostazioni proxy del browser Internet per la rete Account del servizio completando la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="873db-225">If your watcher node computer is located outside your perimeter network, you will probably not be able to run the Data Conferencing Synthetic Transaction unless you first disable the Windows Internet Explorer® Internet browser proxy settings for the Network Service account by completing the following steps:</span></span>
  
1. <span data-ttu-id="873db-226">Nel computer del nodo Watcher fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Accessori**, fare clic con il pulsante destro del mouse su **prompt dei comandi**e quindi scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="873db-226">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right click **Command Prompt**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="873db-227">Nella finestra della console digitare il comando seguente e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="873db-227">In the console window, type the following command and then press ENTER.</span></span> 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

<span data-ttu-id="873db-228">Nella finestra di comando verrà visualizzato il messaggio seguente:</span><span class="sxs-lookup"><span data-stu-id="873db-228">You will see the following message displayed in the command window:</span></span>
  
<span data-ttu-id="873db-229">BITSAdmin è deprecato e non è garantito per essere disponibile nelle versioni future di Windows.</span><span class="sxs-lookup"><span data-stu-id="873db-229">BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows.</span></span> <span data-ttu-id="873db-230">Gli strumenti di amministrazione per il servizio BITS sono ora forniti dai cmdlet di PowerShell BITS.</span><span class="sxs-lookup"><span data-stu-id="873db-230">Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.</span></span>
  
<span data-ttu-id="873db-231">Impostazioni proxy Internet per l'account NetworkService impostato su NO_PROXY.</span><span class="sxs-lookup"><span data-stu-id="873db-231">Internet proxy settings for account NetworkService set to NO_PROXY.</span></span> 
  
<span data-ttu-id="873db-232">(Connection = default)</span><span class="sxs-lookup"><span data-stu-id="873db-232">(connection = default)</span></span>
  
<span data-ttu-id="873db-233">Questo messaggio indica che sono state disabilitate le impostazioni proxy di Internet Explorer per l'account del servizio di rete.</span><span class="sxs-lookup"><span data-stu-id="873db-233">This message indicates that you have disabled the Internet Explorer proxy settings for the Network Service account.</span></span>
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a><span data-ttu-id="873db-234">Transazione sintetica di messaggistica unificata di Exchange</span><span class="sxs-lookup"><span data-stu-id="873db-234">Exchange Unified Messaging Synthetic Transaction</span></span>

<span data-ttu-id="873db-235">La transazione sintetica della messaggistica unificata di Exchange verifica che gli utenti di test possano connettersi agli account della segreteria telefonica in Exchange.</span><span class="sxs-lookup"><span data-stu-id="873db-235">The Exchange Unified Messaging (UM) synthetic transaction verifies that test users can connect to voicemail accounts homed in Exchange.</span></span>
  
<span data-ttu-id="873db-236">Gli utenti di test dovranno essere preconfigurati con gli account della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="873db-236">The test users will need to be preconfigured with voicemail accounts.</span></span> 
  
### <a name="persistent-chat-synthetic-transaction"></a><span data-ttu-id="873db-237">Transazione sintetica della chat persistente</span><span class="sxs-lookup"><span data-stu-id="873db-237">Persistent Chat Synthetic Transaction</span></span>

<span data-ttu-id="873db-238">Per usare la transazione sintetica della chat persistente, è necessario prima di tutto creare un canale e concedere agli utenti di test le autorizzazioni per usarlo.</span><span class="sxs-lookup"><span data-stu-id="873db-238">To use the Persistent Chat synthetic transaction, you must first create a channel and give the test users permissions to use it.</span></span>
  
<span data-ttu-id="873db-239">È possibile usare la transazione sintetica della chat persistente per configurare questo canale:</span><span class="sxs-lookup"><span data-stu-id="873db-239">You can use the Persistent Chat synthetic transaction to configure this channel:</span></span> 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

<span data-ttu-id="873db-240">È necessario eseguire questa attività di configurazione deve essere eseguita dall'interno dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="873db-240">You must run this setup task must be run from inside the enterprise:</span></span>
  
- <span data-ttu-id="873db-241">Se eseguito da un computer non server, l'utente che esegue il cmdlet deve essere un membro del ruolo CsPersistentChatAdministrators per il controllo di accesso basato sui ruoli (RBAC).</span><span class="sxs-lookup"><span data-stu-id="873db-241">If run from a non-server machine, the user who executes the cmdlet must be a member of the CsPersistentChatAdministrators role for Role-Based Access Control (RBAC).</span></span>
    
- <span data-ttu-id="873db-242">Se eseguito dal server stesso, l'utente che esegue il cmdlet deve essere un membro del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="873db-242">If run from the server itself, the user who executes the cmdlet must be a member of the RTCUniversalServerAdmins group.</span></span>
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a><span data-ttu-id="873db-243">Transazione sintetica chiamata peer-to-peer PSTN</span><span class="sxs-lookup"><span data-stu-id="873db-243">PSTN Peer-to-Peer Call Synthetic Transaction</span></span>

<span data-ttu-id="873db-244">La transazione sintetica Test-CsPstnPeerToPeerCall verifica la possibilità di effettuare e ricevere chiamate tramite una rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="873db-244">The Test-CsPstnPeerToPeerCall synthetic transaction verifies the ability to place and receive calls through a public switched telephone network (PSTN).</span></span>
  
<span data-ttu-id="873db-245">Per eseguire questa transazione sintetica, è necessario configurare:</span><span class="sxs-lookup"><span data-stu-id="873db-245">To run this synthetic transaction, you must configure:</span></span>
  
- <span data-ttu-id="873db-246">Due utenti di test abilitati per UC (un chiamante e un ricevitore).</span><span class="sxs-lookup"><span data-stu-id="873db-246">Two UC-enabled test users (a caller and a receiver).</span></span>
    
- <span data-ttu-id="873db-247">Numeri DID (Direct inwarding Dialing) per ogni account utente.</span><span class="sxs-lookup"><span data-stu-id="873db-247">Direct Inward Dialing (DID) numbers for each user account.</span></span>
    
- <span data-ttu-id="873db-248">Criteri VoIP e route vocali che consentono alle chiamate al numero del destinatario di raggiungere il gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="873db-248">VoIP Policies and Voice routes that allow calls to the receiver's number to reach the PSTN gateway.</span></span>
    
- <span data-ttu-id="873db-249">Un gateway PSTN che accetta chiamate e elementi multimediali che instradano le chiamate al pool Home di un destinatario, in base al numero composto.</span><span class="sxs-lookup"><span data-stu-id="873db-249">A PSTN gateway that accepts call and media that will route calls back to a receiver's home pool, based on the number dialed.</span></span>
    
### <a name="unified-contact-store-synthetic-transaction"></a><span data-ttu-id="873db-250">Transazione sintetica archivio contatti unificato</span><span class="sxs-lookup"><span data-stu-id="873db-250">Unified Contact Store Synthetic Transaction</span></span>

<span data-ttu-id="873db-251">La transazione sintetica archivio contatti unificato verifica la possibilità di Skype for Business Server di recuperare i contatti per conto di un utente da Exchange.</span><span class="sxs-lookup"><span data-stu-id="873db-251">The Unified Contact Store synthetic transaction verifies the ability of Skype for Business Server to retrieve contacts on behalf of a user from Exchange.</span></span>
  
<span data-ttu-id="873db-252">Per usare questa transazione sintetica, è necessario che siano soddisfatte le condizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="873db-252">To use this synthetic transaction, the following conditions must be met:</span></span>
  
- <span data-ttu-id="873db-253">Lyss-Exchange Server to Server Authentication deve essere configurato.</span><span class="sxs-lookup"><span data-stu-id="873db-253">Lyss-Exchange server to server authentication must be configured.</span></span>
    
- <span data-ttu-id="873db-254">Test gli utenti devono avere una cassetta postale di Exchange valida.</span><span class="sxs-lookup"><span data-stu-id="873db-254">Test users must have a valid Exchange mailbox.</span></span>
    
<span data-ttu-id="873db-255">Una volta soddisfatte queste condizioni, è possibile eseguire il cmdlet di Windows PowerShell seguente per eseguire la migrazione degli elenchi di contatti degli utenti di test a Exchange:</span><span class="sxs-lookup"><span data-stu-id="873db-255">After these conditions are met, you can run the following Windows PowerShell cmdlet to migrate the test users' contact lists to Exchange:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

<span data-ttu-id="873db-256">Potrebbe essere necessario un po' di tempo prima che gli elenchi di contatti degli utenti di test vengano migrati in Exchange.</span><span class="sxs-lookup"><span data-stu-id="873db-256">It may take some time for the test user contact lists to migrate to Exchange.</span></span> <span data-ttu-id="873db-257">Per monitorare lo stato di avanzamento della migrazione, è possibile eseguire la stessa riga di comando senza il flag-Setup:</span><span class="sxs-lookup"><span data-stu-id="873db-257">To monitor the migration progress, the same command-line can be run without the -Setup flag:</span></span>
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

<span data-ttu-id="873db-258">Questa riga di comando avrà esito positivo dopo il completamento della migrazione.</span><span class="sxs-lookup"><span data-stu-id="873db-258">This command line will succeed after migration is completed.</span></span>
  
### <a name="xmpp-synthetic-transaction"></a><span data-ttu-id="873db-259">Transazione sintetica XMPP</span><span class="sxs-lookup"><span data-stu-id="873db-259">XMPP Synthetic Transaction</span></span>

<span data-ttu-id="873db-260">La transazione sintetica di messaggistica istantanea (XMPP) Extensible Messaging and Presence richiede la configurazione della funzionalità XMPP con uno o più domini federati.</span><span class="sxs-lookup"><span data-stu-id="873db-260">The Extensible Messaging and Presence Protocol (XMPP) IM synthetic transaction requires that you configure the XMPP feature with one or more federated domains.</span></span>
  
<span data-ttu-id="873db-261">Per abilitare la transazione sintetica XMPP, devi specificare un parametro XmppTestReceiverMailAddress con un account utente in un dominio XMPP instradabile.</span><span class="sxs-lookup"><span data-stu-id="873db-261">To enable the XMPP synthetic transaction, you must provide an XmppTestReceiverMailAddress parameter with a user account at a routable XMPP domain.</span></span> <span data-ttu-id="873db-262">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="873db-262">For example:</span></span>
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

<span data-ttu-id="873db-263">In questo esempio, è necessario che sia presente una regola di Skype for Business Server per instradare i messaggi per litwareinc.com a un gateway XMPP.</span><span class="sxs-lookup"><span data-stu-id="873db-263">In this example, a Skype for Business Server rule will need to exist to route messages for litwareinc.com to an XMPP gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="873db-264">I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="873db-264">XMPP Gateways and proxies were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="873db-265">Per altre informazioni, Vedi [migrazione della Federazione XMPP](../migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="873db-265">See [Migrating XMPP federation](../migration/migrating-xmpp-federation.md) for more information.</span></span>
  
### <a name="video-interop-server-vis-synthetic-transaction"></a><span data-ttu-id="873db-266">Transazione sintetica video Interop Server (VIS)</span><span class="sxs-lookup"><span data-stu-id="873db-266">Video Interop Server (VIS) Synthetic Transaction</span></span>

<span data-ttu-id="873db-267">La transazione sintetica video Interop Server (VIS) richiede il download e l'installazione dei file di supporto delle transazioni sintetiche ([VISSTSupportPackage. msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)).</span><span class="sxs-lookup"><span data-stu-id="873db-267">The Video Interop Server (VIS) synthetic transaction requires that you download and install the synthetic transaction support files ([VISSTSupportPackage.msi](https://www.microsoft.com/en-us/download/details.aspx?id=46921)).</span></span> 
  
<span data-ttu-id="873db-268">Per installare VISSTSupportPackage. msi, verificare che le dipendenze (in requisiti di sistema) per MSI siano già installate.</span><span class="sxs-lookup"><span data-stu-id="873db-268">To install VISSTSupportPackage.msi ensure the dependencies (under System Requirements) for the msi are already installed.</span></span> <span data-ttu-id="873db-269">Eseguire VISSTSupportPackage. msi per eseguire un'installazione semplice.</span><span class="sxs-lookup"><span data-stu-id="873db-269">Run VISSTSupportPackage.msi to do a simple installation.</span></span> <span data-ttu-id="873db-270">Msi installa tutti i file nel percorso seguente: "pacchetto di supporto per le transazioni sintetiche%ProgramFiles%\VIS".</span><span class="sxs-lookup"><span data-stu-id="873db-270">The .msi installs all the files in the following path: "%ProgramFiles%\VIS Synthetic Transaction Support Package".</span></span>
  
<span data-ttu-id="873db-271">Per altre informazioni su come eseguire la transazione sintetica di VIS, vedere la documentazione relativa al cmdlet [test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) .</span><span class="sxs-lookup"><span data-stu-id="873db-271">For more details on how to run the VIS Synthetic Transaction refer to the documentation for the [Test-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) cmdlet.</span></span>
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a><span data-ttu-id="873db-272">Modifica della frequenza di esecuzione per le transazioni sintetiche</span><span class="sxs-lookup"><span data-stu-id="873db-272">Changing the Run Frequency for Synthetic Transactions</span></span>
<span data-ttu-id="873db-273"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="873db-273"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="873db-274">Per impostazione predefinita, le transazioni sintetiche verranno eseguite con gli utenti configurati ogni 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="873db-274">By default, synthetic transactions will run with the configured users every 15 minutes.</span></span> <span data-ttu-id="873db-275">Le transazioni sintetiche vengono eseguite sequenzialmente all'interno di un set di utenti per evitare che due transazioni sintetiche siano in conflitto tra loro.</span><span class="sxs-lookup"><span data-stu-id="873db-275">Synthetic transactions are run sequentially within a set of users to avoid two synthetic transactions from conflicting with each other.</span></span> <span data-ttu-id="873db-276">Un intervallo più lungo è necessario per consentire il completamento di tutte le transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="873db-276">A longer interval is needed to provide time for all synthetic transactions to complete.</span></span>
  
<span data-ttu-id="873db-277">Se è consigliabile eseguire più di frequente le transazioni sintetiche, il numero di transazioni sintetiche eseguito con un determinato set di utenti dovrebbe essere ridotto in modo che i test possano essere completati nell'intervallo di tempo desiderato con alcuni buffer per i ritardi di rete occasionali.</span><span class="sxs-lookup"><span data-stu-id="873db-277">If it is desirable to run synthetic transactions more frequently, the number of synthetic transactions run with a given set of users should be decreased so that the tests can complete in the desired time range with some buffer for occasional network delays.</span></span> <span data-ttu-id="873db-278">Se è consigliabile eseguire più transazioni sintetiche, creare più set di utenti per eseguire altre transazioni sintetiche.</span><span class="sxs-lookup"><span data-stu-id="873db-278">If running more synthetic transactions is desirable, create more user sets to run additional synthetic transactions.</span></span>
  
<span data-ttu-id="873db-279">Per modificare la frequenza con cui vengono eseguite le transazioni sintetiche, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="873db-279">To change the frequency at which synthetic transactions run, follow these steps:</span></span>
  
1. <span data-ttu-id="873db-280">Aprire System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="873db-280">Open System Center Operations Manager.</span></span> <span data-ttu-id="873db-281">Fare clic su sezione Creazione.</span><span class="sxs-lookup"><span data-stu-id="873db-281">Click Authoring section.</span></span> <span data-ttu-id="873db-282">Fare clic su sezione regole (in creazione)</span><span class="sxs-lookup"><span data-stu-id="873db-282">Click Rules section (under Authoring)</span></span>
    
2. <span data-ttu-id="873db-283">Nella sezione regole individuare la regola con il nome "regola di raccolta delle prestazioni per le transazioni sintetiche principali"</span><span class="sxs-lookup"><span data-stu-id="873db-283">In the Rules section, find the rule with the name "Main Synthetic Transaction Runner Performance Collection Rule"</span></span>
    
3. <span data-ttu-id="873db-284">Fare clic con il pulsante destro del mouse sulla regola e scegliere sostituzioni, selezionare Sostituisci la regola e quindi selezionare "per tutti gli oggetti della classe: Watcher del pool"</span><span class="sxs-lookup"><span data-stu-id="873db-284">Right click the rule, and select Overrides, select Override the Rule, and then select "For All objects of class: Pool Watcher"</span></span>
    
4. <span data-ttu-id="873db-285">Nella finestra Proprietà override selezionare Nome parametro "frequenza" e impostare il valore di override su quello desiderato.</span><span class="sxs-lookup"><span data-stu-id="873db-285">In the Override Properties window, select Parameter Name "Frequency", and set the Override Value to the desired one.</span></span>
    
5. <span data-ttu-id="873db-286">Nella stessa finestra selezionare il Management Pack a cui deve essere applicato questo override</span><span class="sxs-lookup"><span data-stu-id="873db-286">In the same window, select the Management pack to which this override needs to be applied</span></span>
    
## <a name="using-rich-logging-for-synthetic-transactions"></a><span data-ttu-id="873db-287">Uso della registrazione avanzata per le transazioni sintetiche</span><span class="sxs-lookup"><span data-stu-id="873db-287">Using Rich Logging for Synthetic Transactions</span></span>
<span data-ttu-id="873db-288"><a name="special_synthetictrans"> </a></span><span class="sxs-lookup"><span data-stu-id="873db-288"><a name="special_synthetictrans"> </a></span></span>

<span data-ttu-id="873db-289">Le transazioni sintetiche risultano estremamente utili per identificare i problemi con il sistema.</span><span class="sxs-lookup"><span data-stu-id="873db-289">Synthetic transactions prove extremely useful in helping to identify issues with the system.</span></span> <span data-ttu-id="873db-290">Ad esempio, il cmdlet Test-CsRegistration potrebbe avvisare gli amministratori del fatto che gli utenti avevano difficoltà a registrarsi con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="873db-290">For example, the Test-CsRegistration cmdlet could alert administrators to the fact that users were having difficulty registering with Skype for Business Server.</span></span> <span data-ttu-id="873db-291">Tuttavia, potrebbero essere necessari dettagli aggiuntivi per determinare la causa effettiva di un errore.</span><span class="sxs-lookup"><span data-stu-id="873db-291">However, additional details may be needed to determine the actual cause of a failure.</span></span>
  
<span data-ttu-id="873db-292">Per questo motivo, le transazioni sintetiche garantiscono una registrazione avanzata.</span><span class="sxs-lookup"><span data-stu-id="873db-292">For this reason, synthetic transactions provide rich logging.</span></span> <span data-ttu-id="873db-293">Con la registrazione avanzata, per ogni attività eseguita da una transazione sintetica, vengono registrate le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="873db-293">With rich logging, for each activity that a synthetic transaction undertakes, the following information is recorded:</span></span>
  
- <span data-ttu-id="873db-294">L'ora in cui è stata avviata l'attività.</span><span class="sxs-lookup"><span data-stu-id="873db-294">The time that the activity started.</span></span>
    
- <span data-ttu-id="873db-295">L'ora di completamento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="873db-295">The time that the activity finished.</span></span>
    
- <span data-ttu-id="873db-296">Azione eseguita (ad esempio, creazione, partecipazione o uscita da una conferenza; accesso a Skype for Business Server; invio di un messaggio istantaneo).</span><span class="sxs-lookup"><span data-stu-id="873db-296">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Skype for Business Server; sending an instant message).</span></span>
    
- <span data-ttu-id="873db-297">Messaggi informativi, dettagliati, di avviso o di errore generati durante l'esecuzione dell'attività</span><span class="sxs-lookup"><span data-stu-id="873db-297">Informational, verbose, warning, or error messages generated when the activity ran</span></span>
    
- <span data-ttu-id="873db-298">Messaggi di registrazione SIP.</span><span class="sxs-lookup"><span data-stu-id="873db-298">SIP registration messages.</span></span>
    
- <span data-ttu-id="873db-299">Record di eccezioni o codici di diagnostica generati durante l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="873db-299">Exception records or diagnostic codes generated when the activity ran.</span></span>
    
- <span data-ttu-id="873db-300">Il risultato risultante dall'eseguire l'attività.</span><span class="sxs-lookup"><span data-stu-id="873db-300">The net result of running the activity.</span></span>
    
<span data-ttu-id="873db-301">Queste informazioni vengono generate automaticamente ogni volta che viene eseguita una transazione sintetica, ma non vengono visualizzate o salvate automaticamente in un file di log.</span><span class="sxs-lookup"><span data-stu-id="873db-301">This information is automatically generated each time a synthetic transaction is run, but is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="873db-302">Se si esegue manualmente una transazione sintetica, è possibile usare il parametro OutLoggerVariable per specificare una variabile di Windows PowerShell in cui verranno archiviate le informazioni.</span><span class="sxs-lookup"><span data-stu-id="873db-302">If you are manually running a synthetic transaction, you can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="873db-303">Da qui è possibile usare uno dei due metodi per salvare e/o visualizzare i messaggi di errore nel log RTF in formato XML o HTML.</span><span class="sxs-lookup"><span data-stu-id="873db-303">From there, you have the option of using one of two methods to save and/or view error messages in the rich log in either XML or HTML format.</span></span> 
  
<span data-ttu-id="873db-304">Per recuperare le informazioni sulla risoluzione dei problemi, specificare il parametro OutLoggerVariable, seguito da un nome di variabile scelto:</span><span class="sxs-lookup"><span data-stu-id="873db-304">To retrieve the troubleshooting information, specify the OutLoggerVariable parameter, followed by a variable name that you choose:</span></span>
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> <span data-ttu-id="873db-305">: Non precedere il nome della variabile con il carattere $.</span><span class="sxs-lookup"><span data-stu-id="873db-305">: Do not preface the variable name with the $ character.</span></span> <span data-ttu-id="873db-306">Usare un nome di variabile, ad esempio RegistrationTest (non $RegistrationTest).</span><span class="sxs-lookup"><span data-stu-id="873db-306">Use a variable name such as RegistrationTest (not $RegistrationTest).</span></span> 
  
<span data-ttu-id="873db-307">Quando si esegue questo comando, viene visualizzato l'output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="873db-307">When you run this command, you will see output similar to this:</span></span>
  
<span data-ttu-id="873db-308">FQDN di destinazione: atl-cs-001.litwareinc.com risultato: latenza errore: messaggio di errore 00:00:00: il computer in cui non sono presenti certificati assegnati.</span><span class="sxs-lookup"><span data-stu-id="873db-308">Target Fqdn : atl-cs-001.litwareinc.com Result : Failure Latency : 00:00:00 Error Message : This machine does not have any assigned certificates.</span></span> <span data-ttu-id="873db-309">Diagnosi: è possibile accedere a informazioni molto più dettagliate per questo errore che non solo il messaggio di errore visualizzato qui.</span><span class="sxs-lookup"><span data-stu-id="873db-309">Diagnosis :You can access much more detailed information for this failure than just the error message shown here.</span></span> <span data-ttu-id="873db-310">Per accedere a queste informazioni in formato HTML, usare un comando simile a quello per salvare le informazioni archiviate nella variabile RegistrationTest in un file HTML:</span><span class="sxs-lookup"><span data-stu-id="873db-310">To access this information in HTML format, use a command similar to this one to save the information stored in the variable RegistrationTest to an HTML file:</span></span>
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

<span data-ttu-id="873db-311">In alternativa, puoi usare il metodo ToXML () per salvare i dati in un file XML:</span><span class="sxs-lookup"><span data-stu-id="873db-311">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

<span data-ttu-id="873db-312">Puoi visualizzare questi file usando Windows Internet Explorer, Microsoft Visual Studio o qualsiasi altra applicazione in grado di aprire file HTML/XML.</span><span class="sxs-lookup"><span data-stu-id="873db-312">You can view these files by using Windows Internet Explorer, Microsoft Visual Studio, or any other application capable of opening HTML/XML files.</span></span>
  
<span data-ttu-id="873db-313">Le transazioni sintetiche eseguite dall'interno di System Center Operations Manager generano automaticamente questi file di log per gli errori.</span><span class="sxs-lookup"><span data-stu-id="873db-313">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="873db-314">Questi registri non verranno generati se l'esecuzione non riesce prima che Skype for Business Server PowerShell sia in grado di caricare ed eseguire la transazione sintetica.</span><span class="sxs-lookup"><span data-stu-id="873db-314">These logs will not be generated if the execution fails before Skype for Business Server PowerShell is able to load and run the synthetic transaction.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="873db-315">Per impostazione predefinita, Skype for Business Server Salva i file di log in una cartella non condivisa.</span><span class="sxs-lookup"><span data-stu-id="873db-315">By default, Skype for Business Server saves log files to a folder that is not shared.</span></span> <span data-ttu-id="873db-316">Per rendere questi registri facilmente accessibili, è consigliabile condividere questa cartella.</span><span class="sxs-lookup"><span data-stu-id="873db-316">To make these logs readily accessible, you should share this folder.</span></span> <span data-ttu-id="873db-317">Ad esempio: \\ATL-watcher-001. litwareinc. com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="873db-317">For example: \\atl-watcher-001.litwareinc.com\WatcherNode.</span></span> 
