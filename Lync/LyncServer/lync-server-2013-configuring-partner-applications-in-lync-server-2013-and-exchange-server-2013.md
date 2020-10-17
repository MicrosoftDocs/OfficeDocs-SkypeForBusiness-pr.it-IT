---
title: Configurazione delle applicazioni partner in Lync Server 2013 e Exchange Server 2013
description: Configurazione delle applicazioni partner in Lync Server 2013 e Exchange Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b149642e7b81a3e8befd321c3a62c8ceeeb00eac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548322"
---
# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="912f6-103">Configurazione delle applicazioni partner in Microsoft Lync Server 2013 e Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="912f6-103">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="912f6-104">_**Ultimo argomento modificato:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="912f6-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="912f6-105">L'autenticazione da server a server in genere implica tre entità: i due server che devono comunicare tra loro e un server di token di sicurezza di terze parti.</span><span class="sxs-lookup"><span data-stu-id="912f6-105">Server-to-server authentication typically involves three entities: the two servers that need to communicate with one another, and a third-party security token server.</span></span> <span data-ttu-id="912f6-106">Se due server (ad esempio, il server A e il server B) devono comunicare, in genere entrambi i server cominciano a contattare un server di token e a ottenere un token di sicurezza attendibile.</span><span class="sxs-lookup"><span data-stu-id="912f6-106">If two servers (for example, Server A and Server B) need to communicate, then both of those servers typically start by contacting a token server and obtain a mutually-trusted security token.</span></span> <span data-ttu-id="912f6-107">Server A quindi presentare il token di sicurezza al server B (e viceversa) per garantire l'autenticità e la sua attendibilità.</span><span class="sxs-lookup"><span data-stu-id="912f6-107">Server A then present that security token to Server B (and vice-versa) as a way to guarantee both its authenticity and its trustworthiness.</span></span>

<span data-ttu-id="912f6-108">Tuttavia, questa è una regola generale.</span><span class="sxs-lookup"><span data-stu-id="912f6-108">However, that's a general rule.</span></span> <span data-ttu-id="912f6-109">Lync Server 2013, Microsoft Exchange Server 2013 e Microsoft SharePoint Server 2013 non è necessario utilizzare un server di token di terze parti per comunicare tra loro; Questo perché questi prodotti server possono creare token di sicurezza che possono essere accettati l'uno dall'altro senza la necessità di un server di token separato.</span><span class="sxs-lookup"><span data-stu-id="912f6-109">Lync Server 2013, Microsoft Exchange Server 2013, and Microsoft SharePoint Server 2013 do not need to use a third-party token server when communicating with one another; that's because these server products can create security tokens that can be accepted by one another without the need for a separate token server.</span></span> <span data-ttu-id="912f6-110">Questa funzionalità è disponibile solo in Lync Server 2013, Exchange 2013 e SharePoint Server 2013.</span><span class="sxs-lookup"><span data-stu-id="912f6-110">(This capability is only available in Lync Server 2013, Exchange 2013, and SharePoint Server 2013.</span></span> <span data-ttu-id="912f6-111">Se è necessario configurare l'autenticazione da server a server con altri server, inclusi altri prodotti server Microsoft, sarà necessario eseguire questa operazione utilizzando un server di token di terze parti.</span><span class="sxs-lookup"><span data-stu-id="912f6-111">If you need to set up server-to-server authentication with other servers, including other Microsoft server products, then you will need to do so by using a third-party token server.)</span></span>

<span data-ttu-id="912f6-112">Per configurare l'autenticazione da server a server tra Lync Server e Exchange, è necessario eseguire due operazioni: 1) è necessario assegnare i certificati adeguati a ogni server; e 2) è necessario configurare ogni server come applicazione partner dell'altro server: questo significa che è necessario configurare Lync Server 2013 come applicazione partner per Exchange 2013 ed è necessario configurare Exchange 2013 come applicazione partner per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="912f6-112">In order to set up server-to-server authentication between Lync Server and Exchange you must do two things: 1) you must assign the appropriate certificates to each server; and, 2) you must configure each server to be a partner application of the other server: that means you must configure Lync Server 2013 to be a partner application for Exchange 2013, and you must configure Exchange 2013 to be a partner application for Lync Server 2013.</span></span>

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a><span data-ttu-id="912f6-113">Configurazione di Lync Server 2013 come applicazione partner per Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="912f6-113">Configuring Lync Server 2013 to be a Partner Application for Exchange 2013</span></span>

<span data-ttu-id="912f6-114">Il modo più semplice per configurare Lync Server 2013 come applicazione partner con Exchange 2013 consiste nell'eseguire lo script Configure-EnterprisePartnerApplication.ps1, uno script di Windows PowerShell che viene fornito con Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="912f6-114">The easiest way to configure Lync Server 2013 to be a partner application with Exchange 2013 is to run the Configure-EnterprisePartnerApplication.ps1 script, a Windows PowerShell script that ships with Exchange 2013.</span></span> <span data-ttu-id="912f6-115">Per eseguire questo script, è necessario fornire l'URL per il documento dei metadati di autenticazione di Lync Server. si tratta in genere del nome di dominio completo del pool di Lync Server 2013 seguito dal suffisso/Metadata/JSON/1.</span><span class="sxs-lookup"><span data-stu-id="912f6-115">To run this script, you must provide the URL for the Lync Server authentication metadata document; this will typically be the fully qualified domain name of the Lync Server 2013 pool followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="912f6-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="912f6-116">For example:</span></span>

    https://atl-cs-001.litwareinc.com/metadata/json/1

<span data-ttu-id="912f6-117">Per configurare Lync Server come applicazione partner, aprire Exchange Management Shell ed eseguire un comando simile a questo (presupponendo che Exchange sia stato installato nell'unità C: e che utilizzi il percorso della cartella predefinito):</span><span class="sxs-lookup"><span data-stu-id="912f6-117">To configure Lync Server as a partner application, open the Exchange Management Shell and run a command similar to this (assuming that Exchange has been installed on drive C: and that it uses the default folder path):</span></span>

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

<span data-ttu-id="912f6-118">Dopo aver configurato l'applicazione partner, è consigliabile arrestare e riavviare Internet Information Services (IIS) nei server cassette postali e accesso client di Exchange.</span><span class="sxs-lookup"><span data-stu-id="912f6-118">After configuring the partner application it is recommended that you stop and restart Internet Information Services (IIS) on your Exchange mailbox and client access servers.</span></span> <span data-ttu-id="912f6-119">Per riavviare IIS è possibile utilizzare un comando simile al seguente, che riavvia il servizio sul computer atl-exchange-001:</span><span class="sxs-lookup"><span data-stu-id="912f6-119">You can restart IIS by using a command similar to this, which restarts the service on the computer atl-exchange-001:</span></span>

    iisreset atl-exchange-001

<span data-ttu-id="912f6-120">Questo comando può essere eseguito dall'interno di Exchange Management Shell o da qualsiasi altra finestra di comando eseguita con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="912f6-120">This command can be run from within the Exchange Management Shell or from any other command window run under administrator privileges.</span></span>

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a><span data-ttu-id="912f6-121">Configurazione di Exchange 2013 come applicazione partner per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="912f6-121">Configuring Exchange 2013 to be a Partner Application for Lync Server 2013</span></span>

<span data-ttu-id="912f6-122">Dopo aver configurato Lync Server 2013 come applicazione partner per Exchange 2013, è necessario configurare Exchange in modo che sia un'applicazione partner per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="912f6-122">After you have configured Lync Server 2013 to be a partner application for Exchange 2013, you must then configure Exchange to be a partner application for Lync Server.</span></span> <span data-ttu-id="912f6-123">È possibile eseguire questa operazione utilizzando Lync Server Management Shell e specificando il documento dei metadati di autenticazione per Exchange. si tratta in genere dell'URI del servizio di individuazione automatica di Exchange seguito dal suffisso/Metadata/JSON/1.</span><span class="sxs-lookup"><span data-stu-id="912f6-123">This can be done by using the Lync Server Management Shell and specifying the authentication metadata document for Exchange; this will typically be the URI of the Exchange autodiscover service followed by the suffix /metadata/json/1.</span></span> <span data-ttu-id="912f6-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="912f6-124">For example:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

<span data-ttu-id="912f6-125">In Lync Server, le applicazioni partner vengono configurate utilizzando il cmdlet [New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="912f6-125">In Lync Server, partner applications are configured by using the [New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) cmdlet.</span></span> <span data-ttu-id="912f6-126">Oltre a specificare l'URI dei metadati, è inoltre necessario impostare il livello di attendibilità dell'applicazione su Full. Ciò consentirà a Exchange di rappresentare se stesso e tutti gli utenti autorizzati nell'area di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="912f6-126">In addition to specifying the metadata URI you should also set the application trust level to Full; this will allow Exchange to represent both itself and any authorized user in the realm.</span></span> <span data-ttu-id="912f6-127">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="912f6-127">For example:</span></span>

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

<span data-ttu-id="912f6-128">In alternativa, è possibile creare un'applicazione partner copiando e modificando il codice di script trovato nella documentazione relativa all'autenticazione da server a server di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="912f6-128">Alternatively, you can create a partner application by copying and modifying the script code found in the Lync Server 2013 server-to-server authentication documentation.</span></span> <span data-ttu-id="912f6-129">Per ulteriori informazioni, vedere l'articolo [Managing server-to-Server Authentication (OAuth) e le applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) .</span><span class="sxs-lookup"><span data-stu-id="912f6-129">See the article [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) for more information.</span></span>

<span data-ttu-id="912f6-130">Se le applicazioni partner sono state configurate correttamente sia per Lync Server che per Exchange, ciò significa che è stata configurata correttamente anche l'autenticazione da server a server tra i due prodotti.</span><span class="sxs-lookup"><span data-stu-id="912f6-130">If you have successfully configured partner applications for both Lync Server and Exchange that means that you have also successfully configured server-to-server authentication between the two products.</span></span> <span data-ttu-id="912f6-131">Lync Server 2013 include un cmdlet di Windows PowerShell, [Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15)), che consente di verificare che l'autenticazione da server a server sia stata configurata correttamente e che il servizio di archiviazione di Lync Server sia in grado di connettersi a Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="912f6-131">Lync Server 2013 includes a Windows PowerShell cmdlet, [Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15)), that enables you to verify that server-to-server authentication has been correctly configured and that the Lync Server Storage Service can connect to Exchange 2013.</span></span> <span data-ttu-id="912f6-132">Il cmdlet esegue la connessione alla cassetta postale di un utente di Exchange 2013, scrivendo un elemento nella cartella Cronologia conversazioni per l'utente e quindi facoltativamente eliminando tale elemento.</span><span class="sxs-lookup"><span data-stu-id="912f6-132">The cmdlet does this by connecting to the mailbox of an Exchange 2013 user, writing an item into the Conversation History folder for that user, and then, optionally, deleting that item.</span></span>

<span data-ttu-id="912f6-133">Per testare l'integrazione di Lync Server 2013 ed Exchange 2013, eseguire un comando simile al seguente dall'interno di Lync Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="912f6-133">To test the integration of Lync Server 2013 and Exchange 2013, run a command similar to this from within the Lync Server Management Shell:</span></span>

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="912f6-134">Nel comando precedente, SipUri rappresenta l'indirizzo SIP di un utente con un account su Exchange 2013; il comando avrà esito negativo in questo non è un account utente valido.</span><span class="sxs-lookup"><span data-stu-id="912f6-134">In the preceding command, the SipUri represents the SIP address of a user with an account on Exchange 2013; your command will fail in this is not a valid user account.</span></span>

<span data-ttu-id="912f6-135">Se il test ha esito positivo e la connettività è stata stabilita, è possibile procedere alla configurazione di funzionalità facoltative, ad esempio l'integrazione di archiviazione e l'archivio contatti unificato.</span><span class="sxs-lookup"><span data-stu-id="912f6-135">If the test succeeds and connectivity has been established, you can then proceed to configure optional features such as archiving integration and the unified contact store.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

