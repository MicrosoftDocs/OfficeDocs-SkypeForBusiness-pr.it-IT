---
title: Configurazione di applicazioni partner in Lync Server 2013 ed Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dad815a67dafea510513e334c910a5dbb8a2e82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="09588-102">Configurazione delle applicazioni partner in Microsoft Lync Server 2013 e Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="09588-102">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09588-103">_**Argomento Ultima modifica:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="09588-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="09588-104">L'autenticazione da server a server in genere include tre entità: i due server che devono comunicare tra loro e un server token di sicurezza di terze parti.</span><span class="sxs-lookup"><span data-stu-id="09588-104">Server-to-server authentication typically involves three entities: the two servers that need to communicate with one another, and a third-party security token server.</span></span> <span data-ttu-id="09588-105">Se due server, ad esempio server A e server B, devono comunicare, questi vengono in genere avviati contattando un server token e ottenendo un token di sicurezza attendibile.</span><span class="sxs-lookup"><span data-stu-id="09588-105">If two servers (for example, Server A and Server B) need to communicate, then both of those servers typically start by contacting a token server and obtain a mutually-trusted security token.</span></span> <span data-ttu-id="09588-106">Server A presentare quindi il token di sicurezza al server B (e viceversa) per garantirne l'autenticità e l'attendibilità.</span><span class="sxs-lookup"><span data-stu-id="09588-106">Server A then present that security token to Server B (and vice-versa) as a way to guarantee both its authenticity and its trustworthiness.</span></span>

<span data-ttu-id="09588-107">Tuttavia, questa è una regola generale.</span><span class="sxs-lookup"><span data-stu-id="09588-107">However, that's a general rule.</span></span> <span data-ttu-id="09588-108">Lync Server 2013, Microsoft Exchange Server 2013 e Microsoft SharePoint Server 2013 non devono usare un server di token di terze parti quando comunicano tra loro; Questo perché questi prodotti server possono creare token di sicurezza che possono essere accettati uno dall'altro senza la necessità di un server token separato.</span><span class="sxs-lookup"><span data-stu-id="09588-108">Lync Server 2013, Microsoft Exchange Server 2013, and Microsoft SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="09588-109">Questa funzionalità è disponibile solo in Lync Server 2013, Exchange 2013 e SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="09588-109">(This capability is only available in Lync Server 2013, Exchange 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="09588-110">Se è necessario configurare l'autenticazione da server a server con altri server, inclusi altri prodotti server Microsoft, sarà necessario farlo usando un server token di terze parti.</span><span class="sxs-lookup"><span data-stu-id="09588-110">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>

<span data-ttu-id="09588-111">Per configurare l'autenticazione da server a server tra Lync Server e Exchange, è necessario eseguire due operazioni: 1) è necessario assegnare i certificati appropriati a ogni server. e 2) è necessario configurare ogni server come applicazione partner dell'altro server: ciò significa che è necessario configurare Lync Server 2013 come applicazione partner per Exchange 2013 ed è necessario configurare Exchange 2013 come applicazione partner per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="09588-111">In order to set up server-to-server authentication between Lync Server and Exchange you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Lync Server 2013 to be a partner application for Exchange 2013, and you must configure Exchange 2013 to be a partner application for Lync Server 2013.</span></span>

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a><span data-ttu-id="09588-112">Configurazione di Lync Server 2013 come applicazione partner per Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="09588-112">Configuring Lync Server 2013 to be a Partner Application for Exchange 2013</span></span>

<span data-ttu-id="09588-113">Il modo più semplice per configurare Lync Server 2013 come applicazione partner con Exchange 2013 consiste nell'eseguire lo script Configure-EnterprisePartnerApplication. ps1, uno script di Windows PowerShell fornito con Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="09588-113">The easiest way to configure Lync Server 2013 to be a partner application with Exchange 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange 2013.</span></span> <span data-ttu-id="09588-114">Per eseguire questo script, è necessario specificare l'URL per il documento di metadati dell'autenticazione di Lync Server. in genere sarà il nome di dominio completo del pool di Lync Server 2013 seguito dal suffisso/Metadata/JSON/1.</span><span class="sxs-lookup"><span data-stu-id="09588-114">To run this script, you must provide the URL for the Lync Server authentication metadata document; this will typically be the fully qualified domain name of the Lync Server 2013 pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="09588-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="09588-115">For example:</span></span>

    https://atl-cs-001.litwareinc.com/metadata/json/1

<span data-ttu-id="09588-116">Per configurare Lync Server come applicazione partner, aprire Exchange Management Shell ed eseguire un comando simile a questo (presupponendo che Exchange sia stato installato nell'unità C: e che usi il percorso della cartella predefinito):</span><span class="sxs-lookup"><span data-stu-id="09588-116">To configure Lync Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

<span data-ttu-id="09588-117">Dopo aver configurato l'applicazione partner, è consigliabile arrestare e riavviare Internet Information Services (IIS) nella cassetta postale di Exchange e nei server Accesso client.</span><span class="sxs-lookup"><span data-stu-id="09588-117">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="09588-118">È possibile riavviare IIS usando un comando simile a questo, che riavvia il servizio nel computer ATL-Exchange-001:</span><span class="sxs-lookup"><span data-stu-id="09588-118">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="09588-119">Questo comando può essere eseguito dall'interno di Exchange Management Shell o da qualsiasi altra finestra di comando eseguita in privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="09588-119">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a><span data-ttu-id="09588-120">Configurazione di Exchange 2013 per un'applicazione partner per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09588-120">Configuring Exchange 2013 to be a Partner Application for Lync Server 2013</span></span>

<span data-ttu-id="09588-121">Dopo aver configurato Lync Server 2013 come applicazione partner per Exchange 2013, è necessario configurare Exchange in un'applicazione partner per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="09588-121">After you have configured Lync Server 2013 to be a partner application for Exchange 2013, you must then configure Exchange to be a partner application for Lync Server.</span></span> <span data-ttu-id="09588-122">Questa operazione può essere eseguita tramite Lync Server Management Shell e specificando il documento di metadati di autenticazione per Exchange. si tratta in genere dell'URI del servizio di individuazione automatica di Exchange seguito dal suffisso/Metadata/JSON/1.</span><span class="sxs-lookup"><span data-stu-id="09588-122">This can be done by using the Lync Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="09588-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="09588-123">For example:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

<span data-ttu-id="09588-124">In Lync Server le applicazioni partner vengono configurate tramite il cmdlet [New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="09588-124">In Lync Server, partner applications are configured by using the [New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="09588-125">Oltre a specificare l'URI di metadati, devi anche impostare il livello di attendibilità dell'applicazione su completo. Ciò consentirà a Exchange di rappresentare se stesso e qualsiasi utente autorizzato nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="09588-125">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="09588-126">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="09588-126">For example:</span></span>

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

<span data-ttu-id="09588-127">In alternativa, è possibile creare un'applicazione partner copiando e modificando il codice di script trovato nella documentazione di autenticazione server-server di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="09588-127">Alternatively, you can create a partner application by copying and modifying the script code found in the Lync Server 2013 server-to-server authentication documentation.</span></span> <span data-ttu-id="09588-128">Per altre informazioni, vedere l'articolo sulla [gestione dell'autenticazione da server a server (OAuth) e delle applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) .</span><span class="sxs-lookup"><span data-stu-id="09588-128">See the article [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) for more information.</span></span>

<span data-ttu-id="09588-129">Se sono state configurate correttamente le applicazioni partner sia per Lync Server che per Exchange, ciò significa che è stata configurata anche l'autenticazione da server a server tra i due prodotti.</span><span class="sxs-lookup"><span data-stu-id="09588-129">If you have successfully configured partner applications for both Lync Server and Exchange that means that you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="09588-130">Lync Server 2013 include un cmdlet di Windows PowerShell, [Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15)), che consente di verificare che l'autenticazione da server a server sia stata configurata correttamente e che il servizio di archiviazione di Lync Server possa connettersi a Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="09588-130">Lync Server 2013 includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15)), that enables you to verify that server-to-server authentication has been correctly configured and that the Lync Server Storage Service can connect to Exchange 2013.</span></span> <span data-ttu-id="09588-131">Il cmdlet esegue questa operazione connettendosi alla cassetta postale di un utente di Exchange 2013, scrivendo un elemento nella cartella Cronologia conversazioni per l'utente e quindi facoltativamente eliminando tale elemento.</span><span class="sxs-lookup"><span data-stu-id="09588-131">The cmdlet does this by connecting to the mailbox of an Exchange 2013 user, writing an item into the Conversation History folder for that user, and then, optionally, deleting that item.</span></span>

<span data-ttu-id="09588-132">Per testare l'integrazione di Lync Server 2013 ed Exchange 2013, eseguire un comando simile a questo da Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="09588-132">To test the integration of Lync Server 2013 and Exchange 2013, run a command similar to this from within the Lync Server Management Shell:</span></span>

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="09588-133">Nel comando precedente, SipUri rappresenta l'indirizzo SIP di un utente con un account in Exchange 2013; il comando non riuscirà in questo caso non è un account utente valido.</span><span class="sxs-lookup"><span data-stu-id="09588-133">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange 2013; your command will fail in this is not a valid user account.</span></span>

<span data-ttu-id="09588-134">Se il test ha esito positivo e la connettività è stata stabilita, è possibile procedere alla configurazione di funzionalità facoltative, ad esempio l'integrazione di archiviazione e l'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="09588-134">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

