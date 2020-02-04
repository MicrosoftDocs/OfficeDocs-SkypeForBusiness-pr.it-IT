---
title: "Lync Server 2013: prerequisiti per l'integrazione con Exchange Server 2013"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: ea22beb9-c02e-47cb-836d-97a556969052
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721919(v=OCS.15)
ms:contentKeyID: 49733853
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a381f765c9c91e9c5e218d66320d542a11bf878
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="d958a-102">Prerequisiti per l'integrazione di Microsoft Lync Server 2013 e Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="d958a-102">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d958a-103">_**Argomento Ultima modifica:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="d958a-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="d958a-104">Prima di poter integrare Microsoft Lync Server 2013 e Microsoft Exchange Server 2013, è necessario assicurarsi che tutte le operazioni preliminari siano state completate.</span><span class="sxs-lookup"><span data-stu-id="d958a-104">Before you can integrate Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 you must ensure that all the prerequisite steps have been completed.</span></span> <span data-ttu-id="d958a-105">Come ci si potrebbe aspettare, l'integrazione non può essere eseguita fino a quando Exchange 2013 e Lync Server 2013 sono completamente installati e operativi.</span><span class="sxs-lookup"><span data-stu-id="d958a-105">As you might expect, integration cannot take place until both Exchange 2013 and Lync Server 2013 are fully installed and up and running.</span></span> <span data-ttu-id="d958a-106">Per informazioni dettagliate sull'installazione di Exchange, vedere la documentazione relativa alla pianificazione e [http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539)distribuzione di Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="d958a-106">For details about installing Exchange, see the Exchange 2013 Planning and Deployment documentation at [http://go.microsoft.com/fwlink/p/?LinkId=268539](http://go.microsoft.com/fwlink/p/?linkid=268539).</span></span> <span data-ttu-id="d958a-107">Per informazioni dettagliate sull'installazione di Lync Server 2013, vedere la documentazione relativa alla [http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806)pianificazione e alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d958a-107">For details about installing Lync Server 2013, see the planning and deployment documentation at [http://go.microsoft.com/fwlink/p/?LinkId=254806](http://go.microsoft.com/fwlink/p/?linkid=254806).</span></span>

<span data-ttu-id="d958a-108">Una volta eseguiti i server, è necessario assegnare certificati di autenticazione da server a server a Lync Server 2013 ed Exchange 2013; questi certificati consentono a Lync Server e Exchange di scambiare informazioni e comunicare tra loro.</span><span class="sxs-lookup"><span data-stu-id="d958a-108">After the servers are up and running you must assign server-to-server authentication certificates to both Lync Server 2013 and Exchange 2013; these certificates allow Lync Server and Exchange to exchange information and to communicate with one another.</span></span> <span data-ttu-id="d958a-109">Quando si installa Exchange 2013, viene creato un certificato autofirmato con il nome certificato di autenticazione di Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="d958a-109">When you install Exchange 2013, a self-signed certificate with the name Microsoft Exchange Server Auth Certificate is created for you.</span></span> <span data-ttu-id="d958a-110">Questo certificato, disponibile nell'archivio certificati del computer locale, deve essere usato per l'autenticazione da server a server in Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="d958a-110">This certificate, which can be found in the local computer certificate store, should be used for server-to-server authentication on Exchange 2013.</span></span> <span data-ttu-id="d958a-111">Per informazioni dettagliate sull'assegnazione di certificati in Exchange 2013, vedere "configurare il flusso di posta e l' [http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540)accesso client".</span><span class="sxs-lookup"><span data-stu-id="d958a-111">For details about assigning certificates in Exchange 2013, see "Configure Mail Flow and Client Access" at [http://go.microsoft.com/fwlink/p/?LinkId=268540](http://go.microsoft.com/fwlink/p/?linkid=268540).</span></span>

<span data-ttu-id="d958a-112">Per Lync Server 2013 è possibile usare un certificato di Lync Server esistente come certificato di autenticazione da server a server. ad esempio, il certificato predefinito può essere usato anche come certificato OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="d958a-112">For Lync Server 2013 you can use an existing Lync Server certificate as your server-to-server authentication certificate; for example, your default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="d958a-113">Lync Server 2013 consente di usare qualsiasi certificato del server Web come certificato per l'autenticazione da server a server purché:</span><span class="sxs-lookup"><span data-stu-id="d958a-113">Lync Server 2013 allows you to use any Web server certificate as the certificate for server-to-server authentication provided that:</span></span>

  - <span data-ttu-id="d958a-114">Il certificato include il nome del dominio SIP nel campo oggetto.</span><span class="sxs-lookup"><span data-stu-id="d958a-114">The certificate includes the name of your SIP domain in the Subject field.</span></span>

  - <span data-ttu-id="d958a-115">Lo stesso certificato è configurato come certificato OAuthTokenIssuer in tutti i server front-end.</span><span class="sxs-lookup"><span data-stu-id="d958a-115">The same certificate is configured as the OAuthTokenIssuer certificate on all of your Front End Servers.</span></span>

  - <span data-ttu-id="d958a-116">Il certificato ha una lunghezza di almeno 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="d958a-116">The certificate has a length of at least 2048 bits.</span></span>

<span data-ttu-id="d958a-117">Per informazioni dettagliate sui certificati di autenticazione da server a server per Microsoft Lync Server 2013, vedere [assegnazione di un certificato di autenticazione server-server a Microsoft Lync server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="d958a-117">For details about server-to-server authentication certificates for Microsoft Lync Server 2013, see [Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).</span></span>

<span data-ttu-id="d958a-118">Dopo aver assegnato i certificati, è necessario configurare il servizio di individuazione automatica in Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="d958a-118">After the certificates have been assigned you must then configure the autodiscover service on Exchange 2013.</span></span> <span data-ttu-id="d958a-119">In Exchange 2013 il servizio di individuazione automatica configura i profili utente e consente l'accesso ai servizi di Exchange quando gli utenti accedono al sistema.</span><span class="sxs-lookup"><span data-stu-id="d958a-119">In Exchange 2013, the autodiscover service configures user profiles and provides access to Exchange services when users log on to the system.</span></span> <span data-ttu-id="d958a-120">Gli utenti presentano il servizio di individuazione automatica con l'indirizzo di posta elettronica e la password; a sua volta, i servizi conferiscono all'utente informazioni come:</span><span class="sxs-lookup"><span data-stu-id="d958a-120">Users present the autodiscover service with their email address and password; in turn, the services provide the user with information such as:</span></span>

  - <span data-ttu-id="d958a-121">Informazioni sulla connessione per la connettività interna ed esterna a Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="d958a-121">Connection information for both internal and external connectivity to Exchange 2013.</span></span>

  - <span data-ttu-id="d958a-122">Posizione del server delle cassette postali dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d958a-122">The location of the user’s Mailbox server.</span></span>

  - <span data-ttu-id="d958a-123">URL per le funzionalità di Outlook, ad esempio informazioni sulla disponibilità, messaggistica unificata e Rubrica fuori rete.</span><span class="sxs-lookup"><span data-stu-id="d958a-123">URLs for Outlook features such as free/busy information, Unified Messaging, and the offline address book.</span></span>

  - <span data-ttu-id="d958a-124">Impostazioni del server Outlook Anywhere.</span><span class="sxs-lookup"><span data-stu-id="d958a-124">Outlook Anywhere server settings.</span></span>

<span data-ttu-id="d958a-125">Il servizio di individuazione automatica deve essere configurato prima di poter integrare Lync Server 2013 ed Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="d958a-125">The autodiscover service must be configured before you can integrate Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="d958a-126">Puoi verificare se il servizio di individuazione automatica è stato configurato eseguendo il comando seguente da Exchange Management Shell e controllando il valore della proprietà AutoDiscoverServiceInternalUri:</span><span class="sxs-lookup"><span data-stu-id="d958a-126">You can verify whether or not the autodiscover service has been configured by running the following command from the Exchange Management Shell and checking the value of the AutoDiscoverServiceInternalUri property:</span></span>

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

<span data-ttu-id="d958a-127">Se questo valore è vuoto, devi assegnare un URI al servizio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="d958a-127">If this value is blank, you must assign a URI to the autodiscover service.</span></span> <span data-ttu-id="d958a-128">In genere questo URI avrà un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d958a-128">Typically this URI will look similar to this:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

<span data-ttu-id="d958a-129">Puoi assegnare l'URI di individuazione automatica eseguendo un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d958a-129">You can assign the autodiscover URI by running a command similar to this:</span></span>

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

<span data-ttu-id="d958a-130">Per informazioni dettagliate sul servizio di individuazione automatica, vedere "informazioni sul servizio di [http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542)individuazione automatica".</span><span class="sxs-lookup"><span data-stu-id="d958a-130">For details about the autodiscover service, see "Understanding the Autodiscover Service" at [http://go.microsoft.com/fwlink/p/?LinkId=268542](http://go.microsoft.com/fwlink/p/?linkid=268542).</span></span>

<span data-ttu-id="d958a-131">Dopo aver configurato il servizio di individuazione automatica, è necessario modificare le impostazioni di configurazione di Lync server OAuth. Questo assicura che Lync Server sappia dove trovare il servizio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="d958a-131">After the autodiscover service has been configured you must then modify the Lync Server OAuth configuration settings; this ensures that Lync Server knows where to find the autodiscover service.</span></span> <span data-ttu-id="d958a-132">Per modificare le impostazioni di configurazione OAuth in Lync Server 2013, eseguire il comando seguente dall'interno di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d958a-132">To modify the OAuth configuration settings in Lync Server 2013, run the following command from within the Lync Server Management Shell.</span></span> <span data-ttu-id="d958a-133">Quando esegui questo comando, assicurati di specificare l'URI per il servizio di individuazione automatica in uso nel server Exchange e usi **autodiscover. svc** per puntare alla posizione del servizio invece di **autodiscover. XML** (che punta al file XML usato dal servizio):</span><span class="sxs-lookup"><span data-stu-id="d958a-133">When running this command, be sure that you specify the URI to the autodiscover service running on your Exchange server, and that you use **autodiscover.svc** to point to the service location instead of **autodiscover.xml** (which points to the XML file used by the service):</span></span>

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> <span data-ttu-id="d958a-134">Il parametro Identity nel comando precedente è facoltativo. Questo perché Lync Server consente solo di avere una singola raccolta globale di impostazioni di configurazione OAuth.</span><span class="sxs-lookup"><span data-stu-id="d958a-134">The Identity parameter in the preceding command is optional; that's because Lync Server only allows you to have a single, global collection of OAuth configuration settings.</span></span> <span data-ttu-id="d958a-135">Tra le altre cose, questo significa che puoi configurare l'URL di individuazione automatica usando questo comando leggermente più semplice:</span><span class="sxs-lookup"><span data-stu-id="d958a-135">Among other things, that means that you can configure the autodiscover URL by using this slightly-simpler command:</span></span><BR><span data-ttu-id="d958a-136">Set-CsOAuthConfiguration-ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span><span class="sxs-lookup"><span data-stu-id="d958a-136">Set-CsOAuthConfiguration–ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span></span><BR><span data-ttu-id="d958a-137">Se non si ha familiarità con la tecnologia, OAuth è un protocollo di autorizzazione standard usato da numerosi siti Web principali.</span><span class="sxs-lookup"><span data-stu-id="d958a-137">If you are unfamiliar with the technology, OAuth is a standard authorization protocol used by a number of major websites.</span></span> <span data-ttu-id="d958a-138">Con OAuth, le credenziali utente e le password non vengono passate da un computer a un altro.</span><span class="sxs-lookup"><span data-stu-id="d958a-138">With OAuth, user credentials and passwords are not passed from one computer to another.</span></span> <span data-ttu-id="d958a-139">L'autenticazione e l'autorizzazione si basano invece sullo scambio di token di sicurezza. questi token concedono l'accesso a un set di risorse specifico per un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="d958a-139">Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>



</div>

<span data-ttu-id="d958a-140">Oltre a configurare il servizio di individuazione automatica, è necessario creare anche un record DNS per il servizio che punta al server Exchange.</span><span class="sxs-lookup"><span data-stu-id="d958a-140">In addition to configuring the autodiscover service, you must also create a DNS record for the service that points to your Exchange server.</span></span> <span data-ttu-id="d958a-141">Ad esempio, se il servizio di individuazione automatica si trova in autodiscover.litwareinc.com, è necessario creare un record DNS per autodiscover.litwareinc.com che venga risolto nel nome di dominio completo del server di Exchange, ad esempio atl-exchange-001.litwareinc.com).</span><span class="sxs-lookup"><span data-stu-id="d958a-141">For example, if your autodiscover service is located at autodiscover.litwareinc.com you will need to create a DNS record for autodiscover.litwareinc.com that resolves to the fully qualified domain name of your Exchange server (for example, atl-exchange-001.litwareinc.com).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

