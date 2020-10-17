---
title: 'Lync Server 2013: configurazione della messaggistica unificata di Microsoft Exchange Server 2013 per la segreteria telefonica di Lync Server 2013'
description: 'Lync Server 2013: configurazione della messaggistica unificata di Microsoft Exchange Server 2013 per la segreteria telefonica di Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Exchange Server 2013 Unified Messaging for Lync Server 2013 voice mail
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49733573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57576981e419f96734e4bd2ed62a7d203f7b683c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570752"
---
# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a><span data-ttu-id="006b1-103">Configurazione della messaggistica unificata di Microsoft Exchange Server 2013 per la segreteria telefonica di Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="006b1-103">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="006b1-104">_**Ultimo argomento modificato:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="006b1-104">_**Topic Last Modified:** 2013-02-04_</span></span>

<span data-ttu-id="006b1-105">Microsoft Lync Server 2013 consente di archiviare i messaggi in segreteria telefonica in Microsoft Exchange Server 2013; i messaggi vocali verranno quindi visualizzati come messaggi di posta elettronica nelle cassette postali degli utenti.</span><span class="sxs-lookup"><span data-stu-id="006b1-105">Microsoft Lync Server 2013 enables you to have voicemail messages stored in Microsoft Exchange Server 2013; those voicemail messages will then appear as email messages in your users' Inboxes.</span></span> <span data-ttu-id="006b1-106">Questa funzionalità è stata trovata anche nelle edizioni 2010 di Lync Server e Exchange; Tuttavia, il processo di configurazione di questa "messaggistica unificata" è stato semplificato nelle edizioni 2013 grazie all'introduzione del componente del router di chiamata di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="006b1-106">This capability was also found in the 2010 editions of Lync Server and Exchange; however, the process of configuring this "unified messaging" has been simplified in the 2013 editions thanks to the introduction of the UM Call Router component.</span></span> <span data-ttu-id="006b1-107">Questo componente è installato sul server Accesso client di Exchange 2013 e tutte le chiamate alla messaggistica unificata di Exchange (ad esempio una segreteria telefonica) vengono prima instradate attraverso il router di chiamata e quindi vengono reindirizzate al server cassette postali appropriato.</span><span class="sxs-lookup"><span data-stu-id="006b1-107">This component is installed on the Exchange 2013 Client Access server, and all calls to Exchange unified messaging (such as a voicemail) are first routed through the Call Router and then are redirected to the appropriate Mailbox server.</span></span>

<span data-ttu-id="006b1-108">Se è già stata configurata l'autenticazione da server a server tra Lync Server 2013 ed Exchange 2013, si è pronti per l'installazione della messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="006b1-108">If you have already configured server-to-server authentication between Lync Server 2013 and Exchange 2013 then you are ready to setup unified messaging.</span></span> <span data-ttu-id="006b1-109">A tale scopo, è necessario innanzitutto creare e assegnare un nuovo dial plan di messaggistica unificata nel server Exchange.</span><span class="sxs-lookup"><span data-stu-id="006b1-109">To do so, you must first create and assign a new unified messaging dial plan on your Exchange server.</span></span> <span data-ttu-id="006b1-110">Ad esempio, questi due comandi (eseguiti dall'interno di Exchange Management Shell) configurano un nuovo dial plan a tre cifre per Exchange:</span><span class="sxs-lookup"><span data-stu-id="006b1-110">For example, these two commands (run from within the Exchange Management Shell) configure a new 3-digit dial plan for Exchange:</span></span>

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="006b1-p103">Nel primo comando dell'esempio, il parametro VoIPSecurity e il valore del parametro "Secured" indicano che il canale di segnale è crittografato tramite Transport Layer Security (TLS). Il parametro URIType "SipName" indica che i messaggi verranno inviati e ricevuti tramite il protocollo SIP e il valore 1 per CountryOrRegionCode indica che il dial plan si applica agli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="006b1-p103">In the first command in the example, the VoIPSecurity parameter, and the parameter value "Secured" indicate that the signaling channel is encrypted by using Transport Layer Security (TLS). The URIType "SipName" indicates that messages will be sent and received using the SIP protocol, and the CountryOrRegionCode of 1 indicates that the dial plan applies to the US.</span></span>

<span data-ttu-id="006b1-113">Nel secondo comando il valore di parametro passato al parametro ConfiguredInCountryOrRegionGroups specifica quali gruppi nazionali è possibile utilizzare con questo dial plan.</span><span class="sxs-lookup"><span data-stu-id="006b1-113">In the second command, the parameter value passed to the ConfiguredInCountryOrRegionGroups parameter specifies the in-country groups that can be used with this dial plan.</span></span> <span data-ttu-id="006b1-114">Il valore del parametro "Anywhere \* , \* , \* " consente di impostare gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="006b1-114">The parameter value "Anywhere,\*,\*,\*" sets the following:</span></span>

  - <span data-ttu-id="006b1-115">Nome gruppo</span><span class="sxs-lookup"><span data-stu-id="006b1-115">Group name ("Anywhere")</span></span>

  - <span data-ttu-id="006b1-116">AllowedNumberString ( \* un carattere jolly che indica che è consentita una stringa di numero qualsiasi)</span><span class="sxs-lookup"><span data-stu-id="006b1-116">AllowedNumberString (\*, a wildcard character indicating that any number string is allowed)</span></span>

  - <span data-ttu-id="006b1-117">DialNumberString ( \* un carattere jolly che indica che è consentito qualsiasi numero composto)</span><span class="sxs-lookup"><span data-stu-id="006b1-117">DialNumberString (\*, a wildcard character indicating that any dialed number is allowed)</span></span>

  - <span data-ttu-id="006b1-118">TextComment ( \* un carattere jolly che indica che è consentito qualsiasi comando di testo)</span><span class="sxs-lookup"><span data-stu-id="006b1-118">TextComment (\*, a wildcard character indicating that any text command is allowed)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="006b1-119">Se si crea un nuovo dial plan, verrà creato anche un criterio cassetta postale predefinito.</span><span class="sxs-lookup"><span data-stu-id="006b1-119">Creating a new dial plan will also create a Default Mailbox Policy.</span></span>



</div>

<span data-ttu-id="006b1-120">Dopo aver creato e configurato il nuovo dial plan, è necessario aggiungerlo al server di messaggistica unificata, quindi impostare la modalità di avvio su "Doppio".</span><span class="sxs-lookup"><span data-stu-id="006b1-120">After creating and configuring the new dial plan you must add the new dial plan to your unified messaging server and then modify the startup mode of that server; in particular, you must set the startup mode to "Dual".</span></span> <span data-ttu-id="006b1-121">È possibile eseguire entrambe queste attività dall'interno di Exchange Management Shell:</span><span class="sxs-lookup"><span data-stu-id="006b1-121">You can perform both of these tasks from within the Exchange Management Shell:</span></span>

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

<span data-ttu-id="006b1-122">Dopo aver configurato il server Messaggistica unificata, è necessario eseguire il cmdlet Enable-ExchangeCertificate per assicurarsi che il certificato di Exchange venga applicato al servizio di messaggistica unificata:</span><span class="sxs-lookup"><span data-stu-id="006b1-122">After the unified messaging server has been configured you should next run the Enable-ExchangeCertificate cmdlet to ensure that your Exchange certificate is applied to the unified messaging service:</span></span>

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

<span data-ttu-id="006b1-p106">Dopo avere assegnato correttamente il certificato, è quindi necessario arrestare e riavviare il servizio MsExchangeUM sul server di messaggistica unificata. È necessario arrestare e riavviare il servizio ogni volta che si modifica la modalità di avvio.</span><span class="sxs-lookup"><span data-stu-id="006b1-p106">After the certificate has been correctly assigned you must then stop and restart the MsExchangeUM service on the unified messaging server. This service must be stopped and restarted any time you change the startup mode.</span></span>

<span data-ttu-id="006b1-125">Al termine della configurazione del server di messaggistica unificata, è quindi possibile configurare il Router chiamate di messaggistica unificata:</span><span class="sxs-lookup"><span data-stu-id="006b1-125">After finishing configuration of the unified messaging server you can then configure the UM Call Router:</span></span>

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

<span data-ttu-id="006b1-126">Dato che la modalità di avvio è stata modificata, è necessario arrestare e riavviare il servizio MsExchangeUMCR nel computer che ospita il router chiamate di messaggistica unificata.</span><span class="sxs-lookup"><span data-stu-id="006b1-126">Because the startup mode has changed you must stop and restart the MsExchangeUMCR service on the computer hosting the UM Call Router.</span></span>

<span data-ttu-id="006b1-p107">Per completare l'impostazione della messaggistica unificata, è quindi necessario creare criteri di cassetta postale di messaggistica unificata e utilizzare tali criteri per abilitare la messaggistica unificata per gli utenti. È possibile creare criteri di cassetta postale tramite un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="006b1-p107">To complete the unified messaging setup, you then need to create a UM mailbox policy and then use that policy to enable users for unified messaging. You can create a mailbox policy by using a command similar to this:</span></span>

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

<span data-ttu-id="006b1-129">È possibile abilitare la messaggistica unificata per un utente tramite un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="006b1-129">And you can enable a user for unified messaging by using a command similar to this:</span></span>

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

<span data-ttu-id="006b1-p108">Nel comando precedente, il parametro Extensions rappresenta il numero di interno telefonico dell'utente. In questo esempio l'utente ha l'interno 100.</span><span class="sxs-lookup"><span data-stu-id="006b1-p108">In the preceding command, the Extensions parameter represents the telephone extension number for the user. In this example, the user has the extension number 100.</span></span>

<span data-ttu-id="006b1-132">Dopo averne abilitato la cassetta postale, l'utente kenmyer@litwareinc.com dovrebbe essere in grado di utilizzare la messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="006b1-132">After you have enabled his mailbox, the user kenmyer@litwareinc.com should be able to use Exchange unified messaging.</span></span> <span data-ttu-id="006b1-133">È possibile verificare che l'utente possa connettersi alla messaggistica unificata di Exchange eseguendo il cmdlet [test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="006b1-133">You can verify that the user can connect to Exchange UM by running the [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) cmdlet from within the Lync Server Management Shell:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="006b1-134">Se è presente un secondo utente per cui è stata abilitata la messaggistica unificata, è possibile utilizzare il cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) per verificare che possa lasciare un messaggio della segreteria telefonica per il primo utente.</span><span class="sxs-lookup"><span data-stu-id="006b1-134">If you have a second user who has been enabled for unified messaging you can use the [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) cmdlet to verify that this second user can leave a voicemail message for the first user.</span></span>

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

