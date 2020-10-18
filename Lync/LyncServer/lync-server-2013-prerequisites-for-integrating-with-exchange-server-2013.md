---
title: "Lync Server 2013: prerequisiti per l'integrazione con Exchange Server 2013"
description: "Lync Server 2013: prerequisiti per l'integrazione con Exchange Server 2013."
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
ms.openlocfilehash: 5872fe3ec546997cd0633383fdda7e0549bec83f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579852"
---
# <a name="prerequisites-for-integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="85d1c-103">Prerequisiti per l'integrazione di Microsoft Lync Server 2013 e Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="85d1c-103">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85d1c-104">_**Ultimo argomento modificato:** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="85d1c-104">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="85d1c-105">Prima di poter integrare Microsoft Lync Server 2013 e Microsoft Exchange Server 2013, è necessario assicurarsi che tutti i passaggi preliminari siano stati completati.</span><span class="sxs-lookup"><span data-stu-id="85d1c-105">Before you can integrate Microsoft Lync Server 2013 and Microsoft Exchange Server 2013 you must ensure that all the prerequisite steps have been completed.</span></span> <span data-ttu-id="85d1c-106">Come si può immaginare, l'integrazione non può essere eseguita finché sia Exchange 2013 che Lync Server 2013 sono completamente installati e in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="85d1c-106">As you might expect, integration cannot take place until both Exchange 2013 and Lync Server 2013 are fully installed and up and running.</span></span> <span data-ttu-id="85d1c-107">Per informazioni dettagliate sull'installazione di Exchange, vedere la documentazione relativa alla pianificazione e alla distribuzione di Exchange 2013 all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268539](https://go.microsoft.com/fwlink/p/?linkid=268539) .</span><span class="sxs-lookup"><span data-stu-id="85d1c-107">For details about installing Exchange, see the Exchange 2013 Planning and Deployment documentation at [https://go.microsoft.com/fwlink/p/?LinkId=268539](https://go.microsoft.com/fwlink/p/?linkid=268539).</span></span> <span data-ttu-id="85d1c-108">Per informazioni dettagliate sull'installazione di Lync Server 2013, vedere la documentazione relativa alla pianificazione e alla distribuzione all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=254806](https://go.microsoft.com/fwlink/p/?linkid=254806) .</span><span class="sxs-lookup"><span data-stu-id="85d1c-108">For details about installing Lync Server 2013, see the planning and deployment documentation at [https://go.microsoft.com/fwlink/p/?LinkId=254806](https://go.microsoft.com/fwlink/p/?linkid=254806).</span></span>

<span data-ttu-id="85d1c-109">Dopo l'esecuzione dei server, è necessario assegnare certificati di autenticazione da server a server a Lync Server 2013 ed Exchange 2013; questi certificati consentono a Lync Server e Exchange di scambiare informazioni e comunicare tra loro.</span><span class="sxs-lookup"><span data-stu-id="85d1c-109">After the servers are up and running you must assign server-to-server authentication certificates to both Lync Server 2013 and Exchange 2013; these certificates allow Lync Server and Exchange to exchange information and to communicate with one another.</span></span> <span data-ttu-id="85d1c-110">Quando si installa Exchange 2013, viene creato un certificato autofirmato con il nome del certificato di autenticazione di Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="85d1c-110">When you install Exchange 2013, a self-signed certificate with the name Microsoft Exchange Server Auth Certificate is created for you.</span></span> <span data-ttu-id="85d1c-111">Questo certificato, che può essere trovato nell'archivio certificati del computer locale, deve essere utilizzato per l'autenticazione da server a server in Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="85d1c-111">This certificate, which can be found in the local computer certificate store, should be used for server-to-server authentication on Exchange 2013.</span></span> <span data-ttu-id="85d1c-112">Per informazioni dettagliate sull'assegnazione dei certificati in Exchange 2013, vedere la sezione "configurare il flusso di posta e l'accesso client" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268540](https://go.microsoft.com/fwlink/p/?linkid=268540) .</span><span class="sxs-lookup"><span data-stu-id="85d1c-112">For details about assigning certificates in Exchange 2013, see "Configure Mail Flow and Client Access" at [https://go.microsoft.com/fwlink/p/?LinkId=268540](https://go.microsoft.com/fwlink/p/?linkid=268540).</span></span>

<span data-ttu-id="85d1c-113">Per Lync Server 2013 è possibile utilizzare un certificato di Lync Server esistente come certificato di autenticazione da server a server. ad esempio, il certificato predefinito può essere utilizzato anche come certificato di OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="85d1c-113">For Lync Server 2013 you can use an existing Lync Server certificate as your server-to-server authentication certificate; for example, your default certificate can also be used as the OAuthTokenIssuer certificate.</span></span> <span data-ttu-id="85d1c-114">Lync Server 2013 consente di utilizzare qualsiasi certificato del server Web come certificato per l'autenticazione da server a server purché:</span><span class="sxs-lookup"><span data-stu-id="85d1c-114">Lync Server 2013 allows you to use any Web server certificate as the certificate for server-to-server authentication provided that:</span></span>

  - <span data-ttu-id="85d1c-115">Il certificato includa il nome del dominio SIP nel campo Oggetto.</span><span class="sxs-lookup"><span data-stu-id="85d1c-115">The certificate includes the name of your SIP domain in the Subject field.</span></span>

  - <span data-ttu-id="85d1c-116">Lo stesso certificato sia configurato come certificato OAuthTokenIssuer in tutti i Front End Server.</span><span class="sxs-lookup"><span data-stu-id="85d1c-116">The same certificate is configured as the OAuthTokenIssuer certificate on all of your Front End Servers.</span></span>

  - <span data-ttu-id="85d1c-117">Il certificato abbia una lunghezza di almeno 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="85d1c-117">The certificate has a length of at least 2048 bits.</span></span>

<span data-ttu-id="85d1c-118">Per informazioni dettagliate sui certificati di autenticazione da server a server per Microsoft Lync Server 2013, vedere [assegnazione di un certificato di autenticazione da server a server a Microsoft Lync server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="85d1c-118">For details about server-to-server authentication certificates for Microsoft Lync Server 2013, see [Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md).</span></span>

<span data-ttu-id="85d1c-119">Dopo aver assegnato i certificati, è necessario configurare il servizio di individuazione automatica su Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="85d1c-119">After the certificates have been assigned you must then configure the autodiscover service on Exchange 2013.</span></span> <span data-ttu-id="85d1c-120">In Exchange 2013, il servizio di individuazione automatica configura i profili utente e fornisce l'accesso ai servizi di Exchange quando gli utenti accedono al sistema.</span><span class="sxs-lookup"><span data-stu-id="85d1c-120">In Exchange 2013, the autodiscover service configures user profiles and provides access to Exchange services when users log on to the system.</span></span> <span data-ttu-id="85d1c-121">Gli utenti presentano il servizio di individuazione automatica con l'indirizzo di posta elettronica e la password. a sua incirca, i servizi forniscono all'utente informazioni quali:</span><span class="sxs-lookup"><span data-stu-id="85d1c-121">Users present the autodiscover service with their email address and password; in turn, the services provide the user with information such as:</span></span>

  - <span data-ttu-id="85d1c-122">Informazioni di connessione per la connettività sia interna che esterna a Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="85d1c-122">Connection information for both internal and external connectivity to Exchange 2013.</span></span>

  - <span data-ttu-id="85d1c-123">Posizione del server della cassetta postale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="85d1c-123">The location of the user’s Mailbox server.</span></span>

  - <span data-ttu-id="85d1c-124">URL per caratteristiche Outlook quali le informazioni di libero/occupato, la messaggistica unificata e la rubrica offline.</span><span class="sxs-lookup"><span data-stu-id="85d1c-124">URLs for Outlook features such as free/busy information, Unified Messaging, and the offline address book.</span></span>

  - <span data-ttu-id="85d1c-125">Impostazioni del server Outlook via Internet.</span><span class="sxs-lookup"><span data-stu-id="85d1c-125">Outlook Anywhere server settings.</span></span>

<span data-ttu-id="85d1c-126">È necessario configurare il servizio di individuazione automatica prima di poter integrare Lync Server 2013 ed Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="85d1c-126">The autodiscover service must be configured before you can integrate Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="85d1c-127">È possibile verificare se il servizio di individuazione automatica è stato configurato eseguendo il comando seguente da Exchange Management Shell e controllando il valore della proprietà AutoDiscoverServiceInternalUri:</span><span class="sxs-lookup"><span data-stu-id="85d1c-127">You can verify whether or not the autodiscover service has been configured by running the following command from the Exchange Management Shell and checking the value of the AutoDiscoverServiceInternalUri property:</span></span>

    Get-ClientAccessServer | Select-Object Name, AutoDiscoverServiceInternalUri | Format-List

<span data-ttu-id="85d1c-p106">Se il valore è vuoto, è necessario assegnare un URI al servizio di individuazione automatica. Solitamente l'URI sarà simile a questo:</span><span class="sxs-lookup"><span data-stu-id="85d1c-p106">If this value is blank, you must assign a URI to the autodiscover service. Typically this URI will look similar to this:</span></span>

    https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml

<span data-ttu-id="85d1c-130">Per assegnare l'URI di individuazione automatica, è possibile eseguire un comando simile a questo:</span><span class="sxs-lookup"><span data-stu-id="85d1c-130">You can assign the autodiscover URI by running a command similar to this:</span></span>

    Get-ClientAccessServer | Set-ClientAccessServer -AutoDiscoverServiceInternalUri "https://autodiscover.litwareinc.com/autodiscover/autodiscover.xml"

<span data-ttu-id="85d1c-131">Per informazioni dettagliate sul servizio di individuazione automatica, vedere la sezione "informazioni sul servizio di individuazione automatica" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=268542](https://go.microsoft.com/fwlink/p/?linkid=268542) .</span><span class="sxs-lookup"><span data-stu-id="85d1c-131">For details about the autodiscover service, see "Understanding the Autodiscover Service" at [https://go.microsoft.com/fwlink/p/?LinkId=268542](https://go.microsoft.com/fwlink/p/?linkid=268542).</span></span>

<span data-ttu-id="85d1c-132">Dopo che il servizio di individuazione automatica è stato configurato, è necessario modificare le impostazioni di configurazione di Lync server OAuth. in questo modo, Lync Server è in grado di individuare il servizio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="85d1c-132">After the autodiscover service has been configured you must then modify the Lync Server OAuth configuration settings; this ensures that Lync Server knows where to find the autodiscover service.</span></span> <span data-ttu-id="85d1c-133">Per modificare le impostazioni di configurazione OAuth in Lync Server 2013, eseguire il comando riportato di seguito dall'interno di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="85d1c-133">To modify the OAuth configuration settings in Lync Server 2013, run the following command from within the Lync Server Management Shell.</span></span> <span data-ttu-id="85d1c-134">Quando si esegue questo comando, accertarsi di specificare l'URI per il servizio di individuazione automatica in esecuzione nel server Exchange e di utilizzare **autodiscover. svc** in modo che punti alla posizione del servizio anziché **autodiscover.xml** (che punta al file XML utilizzato dal servizio):</span><span class="sxs-lookup"><span data-stu-id="85d1c-134">When running this command, be sure that you specify the URI to the autodiscover service running on your Exchange server, and that you use **autodiscover.svc** to point to the service location instead of **autodiscover.xml** (which points to the XML file used by the service):</span></span>

    Set-CsOAuthConfiguration -Identity global -ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"

<div>


> [!NOTE]  
> <span data-ttu-id="85d1c-135">Il parametro Identity nel comando precedente è facoltativo. Ciò è dovuto al fatto che Lync Server consente solo di disporre di una singola raccolta globale di impostazioni di configurazione OAuth.</span><span class="sxs-lookup"><span data-stu-id="85d1c-135">The Identity parameter in the preceding command is optional; that's because Lync Server only allows you to have a single, global collection of OAuth configuration settings.</span></span> <span data-ttu-id="85d1c-136">Tra le altre cose, questo significa che è possibile configurare l'URL di individuazione automatica utilizzando questo comando leggermente più semplice:</span><span class="sxs-lookup"><span data-stu-id="85d1c-136">Among other things, that means that you can configure the autodiscover URL by using this slightly-simpler command:</span></span><BR><span data-ttu-id="85d1c-137">Set-CsOAuthConfiguration – ExchangeAutodiscoverUrl " https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc "</span><span class="sxs-lookup"><span data-stu-id="85d1c-137">Set-CsOAuthConfiguration–ExchangeAutodiscoverUrl "https://autodiscover.litwareinc.com/autodiscover/autodiscover.svc"</span></span><BR><span data-ttu-id="85d1c-p109">Per chi non avesse familiarità con la tecnologia, OAuth è un protocollo di autorizzazione standard utilizzato da numerosi siti Web di rilievo. Con OAuth, le credenziali e le password degli utenti non vengono passate da un computer all'altro. L'autenticazione e l'autorizzazione sono invece basate sullo scambio di token di sicurezza. Tali token consentono l'accesso a uno specifico set di risorse per un tempo specifico.</span><span class="sxs-lookup"><span data-stu-id="85d1c-p109">If you are unfamiliar with the technology, OAuth is a standard authorization protocol used by a number of major websites. With OAuth, user credentials and passwords are not passed from one computer to another. Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>



</div>

<span data-ttu-id="85d1c-141">Oltre alla configurazione del servizio di individuazione automatica, è inoltre necessario creare un record DNS per il servizio che punta al server Exchange.</span><span class="sxs-lookup"><span data-stu-id="85d1c-141">In addition to configuring the autodiscover service, you must also create a DNS record for the service that points to your Exchange server.</span></span> <span data-ttu-id="85d1c-142">Ad esempio, se il servizio di individuazione automatica si trova in autodiscover.litwareinc.com, sarà necessario creare un record DNS per autodiscover.litwareinc.com che risolva il nome di dominio completo del server Exchange (ad esempio, atl-exchange-001.litwareinc.com).</span><span class="sxs-lookup"><span data-stu-id="85d1c-142">For example, if your autodiscover service is located at autodiscover.litwareinc.com you will need to create a DNS record for autodiscover.litwareinc.com that resolves to the fully qualified domain name of your Exchange server (for example, atl-exchange-001.litwareinc.com).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

