---
title: 'Lync Server 2013: configurazione della messaggistica unificata di Microsoft Exchange Server 2013 per Lync Server 2013 segreteria telefonica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Exchange Server 2013 Unified Messaging for Lync Server 2013 voice mail
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49733573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e1d2bac84183e6cc274d6bb297c17401b3ff7f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a><span data-ttu-id="8cd51-102">Configurazione della messaggistica unificata di Microsoft Exchange Server 2013 per Microsoft Lync Server 2013 Voice mail</span><span class="sxs-lookup"><span data-stu-id="8cd51-102">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cd51-103">_**Argomento Ultima modifica:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="8cd51-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="8cd51-104">Microsoft Lync Server 2013 consente di archiviare i messaggi della segreteria telefonica in Microsoft Exchange Server 2013; i messaggi della segreteria telefonica verranno quindi visualizzati come messaggi di posta elettronica nelle cassette postali degli utenti.</span><span class="sxs-lookup"><span data-stu-id="8cd51-104">Microsoft Lync Server 2013 enables you to have voicemail messages stored in Microsoft Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> <span data-ttu-id="8cd51-105">Questa funzionalità è stata trovata anche nelle edizioni 2010 di Lync Server e Exchange. Tuttavia, il processo di configurazione di questa "messaggistica unificata" è stato semplificato nelle edizioni 2013 grazie all'introduzione del componente router di chiamata di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="8cd51-105">This capability was also found in the 2010 editions of Lync Server and Exchange; however, the process of configuring this "unified messaging" has been simplified in the 2013 editions thanks to the introduction of the UM Call Router component.</span></span> <span data-ttu-id="8cd51-106">Questo componente è installato nel server di accesso client di Exchange 2013 e tutte le chiamate alla messaggistica unificata di Exchange (ad esempio un messaggio vocale) vengono prima instradate tramite il router di chiamata e quindi vengono reindirizzate al server di cassette postali appropriato.</span><span class="sxs-lookup"><span data-stu-id="8cd51-106">This component is installed on the Exchange 2013 Client Access server, and all calls to Exchange unified messaging (such as a voicemail) are first routed through the Call Router and then are redirected to the appropriate Mailbox server.</span></span>

<span data-ttu-id="8cd51-107">Se è già stata configurata l'autenticazione da server a server tra Lync Server 2013 ed Exchange 2013, si è pronti per la configurazione della messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="8cd51-107">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you are ready to setup unified messaging.</span></span> <span data-ttu-id="8cd51-108">A tale scopo, è necessario prima di tutto creare e assegnare un nuovo dial plan di messaggistica unificata nel server Exchange.</span><span class="sxs-lookup"><span data-stu-id="8cd51-108">To do so, you must first create and assign a new unified messaging dial plan on your Exchange server.</span></span> <span data-ttu-id="8cd51-109">Ad esempio, questi due comandi (eseguiti da Exchange Management Shell) configurano un nuovo dial plan a 3 cifre per Exchange:</span><span class="sxs-lookup"><span data-stu-id="8cd51-109">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="8cd51-110">Nel primo comando dell'esempio, il parametro VoIPSecurity e il valore del parametro "Secured" indicano che il canale di segnalazione viene crittografato con Transport Layer Security (TLS).</span><span class="sxs-lookup"><span data-stu-id="8cd51-110">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicate that the signaling channel is encrypted by using Transport Layer Security (TLS).</span></span> <span data-ttu-id="8cd51-111">URIType "SipName" indica che i messaggi verranno inviati e ricevuti usando il protocollo SIP e il CountryOrRegionCode di 1 indica che il dial plan si applica agli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="8cd51-111">The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>

<span data-ttu-id="8cd51-112">Nel secondo comando, il valore del parametro passato al parametro ConfiguredInCountryOrRegionGroups specifica i gruppi in-Country che possono essere usati con questo dial plan.</span><span class="sxs-lookup"><span data-stu-id="8cd51-112">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="8cd51-113">Il valore del parametro "Anywhere\*,\*,\*," imposta le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8cd51-113">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>

  - <span data-ttu-id="8cd51-114">Nome gruppo ("ovunque")</span><span class="sxs-lookup"><span data-stu-id="8cd51-114">Group name ("Anywhere")</span></span>

  - <span data-ttu-id="8cd51-115">AllowedNumberString (\*, un carattere jolly che indica che è consentita una stringa di numero qualsiasi)</span><span class="sxs-lookup"><span data-stu-id="8cd51-115">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>

  - <span data-ttu-id="8cd51-116">DialNumberString (\*, un carattere jolly che indica che è consentito qualsiasi numero composto)</span><span class="sxs-lookup"><span data-stu-id="8cd51-116">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>

  - <span data-ttu-id="8cd51-117">TextComment (\*, un carattere jolly che indica che è consentito qualsiasi comando di testo)</span><span class="sxs-lookup"><span data-stu-id="8cd51-117">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8cd51-118">La creazione di un nuovo dial plan creerà anche un criterio predefinito per le cassette postali.</span><span class="sxs-lookup"><span data-stu-id="8cd51-118">Creating a new dial plan will also create a Default Mailbox Policy.</span></span>



</div>

<span data-ttu-id="8cd51-119">Dopo aver creato e configurato il nuovo piano di chiamata, è necessario aggiungere il nuovo dial plan al server Messaggistica unificata e quindi modificare la modalità di avvio del server. in particolare, devi impostare la modalità di avvio su "Dual".</span><span class="sxs-lookup"><span data-stu-id="8cd51-119">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="8cd51-120">È possibile eseguire entrambe le attività dall'interno di Exchange Management Shell:</span><span class="sxs-lookup"><span data-stu-id="8cd51-120">You can perform both of these tasks from within the Exchange Management Shell:</span></span>

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

<span data-ttu-id="8cd51-121">Dopo aver configurato il server Messaggistica unificata, è consigliabile eseguire il cmdlet Enable-ExchangeCertificate per verificare che il certificato di Exchange venga applicato al servizio di messaggistica unificata:</span><span class="sxs-lookup"><span data-stu-id="8cd51-121">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

<span data-ttu-id="8cd51-122">Dopo che il certificato è stato assegnato correttamente, è necessario arrestare e riavviare il servizio MsExchangeum nel server Messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="8cd51-122">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server.</span></span> <span data-ttu-id="8cd51-123">Questo servizio deve essere interrotto e riavviato ogni volta che si modifica la modalità di avvio.</span><span class="sxs-lookup"><span data-stu-id="8cd51-123">This service must be stopped and restarted any time you change the startup mode.</span></span>

<span data-ttu-id="8cd51-124">Dopo aver terminato la configurazione del server Messaggistica unificata, è possibile configurare il router di chiamata di messaggistica unificata:</span><span class="sxs-lookup"><span data-stu-id="8cd51-124">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

<span data-ttu-id="8cd51-125">Poiché la modalità di avvio è cambiata, è necessario interrompere e riavviare il servizio MsExchangeUMCR nel computer che ospita il router di chiamata di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="8cd51-125">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>

<span data-ttu-id="8cd51-126">Per completare la configurazione della messaggistica unificata, è necessario creare un criterio cassetta postale di messaggistica unificata e quindi usare questo criterio per consentire agli utenti la messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="8cd51-126">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging.</span></span> <span data-ttu-id="8cd51-127">È possibile creare un criterio cassetta postale usando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="8cd51-127">You can create a mailbox policy by using a command similar to this:</span></span>

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="8cd51-128">Puoi abilitare un utente per la messaggistica unificata usando un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="8cd51-128">And you can enable a user for unified messaging by using a command similar to this:</span></span>

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

<span data-ttu-id="8cd51-129">Nel comando precedente il parametro Extensions rappresenta il numero di interno telefonico per l'utente.</span><span class="sxs-lookup"><span data-stu-id="8cd51-129">In the preceding command, the Extensions parameter represents the telephone extension number for the user.</span></span> <span data-ttu-id="8cd51-130">In questo esempio l'utente ha il numero di interno 100.</span><span class="sxs-lookup"><span data-stu-id="8cd51-130">In this example, the user has the extension number 100.</span></span>

<span data-ttu-id="8cd51-131">Dopo aver abilitato la cassetta postale, l'utente kenmyer@litwareinc.com dovrebbe essere in grado di usare la messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="8cd51-131">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="8cd51-132">Puoi verificare che l'utente possa connettersi alla messaggistica unificata di Exchange eseguendo il cmdlet [test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) da Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="8cd51-132">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) cmdlet from within the Lync Server Management Shell:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="8cd51-133">Se si ha un secondo utente abilitato per la messaggistica unificata, è possibile usare il cmdlet [test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) per verificare che il secondo utente possa uscire da un messaggio della segreteria telefonica per il primo utente.</span><span class="sxs-lookup"><span data-stu-id="8cd51-133">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

