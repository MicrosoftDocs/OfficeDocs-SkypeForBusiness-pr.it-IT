---
title: Gestione dell'autenticazione da server a server (OAuth) e delle applicazioni partner
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing server-to-server authentication (OAuth) and partner applications
ms:assetid: 38848373-c8c6-4097-bf7f-699fe471348d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204817(v=OCS.15)
ms:contentKeyID: 48183894
ms.date: 05/15/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01de2856b8923fff76cf33dda7d7e6ba21889c2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-server-to-server-authentication-oauth-and-partner-applications-in-lync-server-2013"></a><span data-ttu-id="7aa87-102">Gestione dell'autenticazione server-Server (OAuth) e delle applicazioni partner in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7aa87-102">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7aa87-103">_**Argomento Ultima modifica:** 2015-05-14_</span><span class="sxs-lookup"><span data-stu-id="7aa87-103">_**Topic Last Modified:** 2015-05-14_</span></span>

<span data-ttu-id="7aa87-104">Microsoft Lync Server 2013 deve essere in grado di comunicare in modo sicuro e trasparente con altre applicazioni e prodotti server.</span><span class="sxs-lookup"><span data-stu-id="7aa87-104">Microsoft Lync Server 2013 must be able to securely, and seamlessly, communicate with other applications and server products.</span></span> <span data-ttu-id="7aa87-105">Ad esempio, è possibile configurare Lync Server 2013 in modo che i dati dei contatti e/o i dati di archiviazione vengano archiviati in Microsoft Exchange Server 2013. Tuttavia, questa operazione può essere eseguita solo se Lync Server e Exchange sono in grado di comunicare in modo sicuro tra loro.</span><span class="sxs-lookup"><span data-stu-id="7aa87-105">For example, you can configure Lync Server 2013 so that contact data and/or archiving data is stored in Microsoft Exchange Server 2013; however, this can only be done if Lync Server and Exchange are able to securely communicate with one another.</span></span> <span data-ttu-id="7aa87-106">Analogamente, è possibile pianificare una conferenza di Lync Server da Microsoft SharePoint Server; di nuovo, tuttavia, questa operazione può essere eseguita solo se i due server (SharePoint e Lync Server) si fidano a vicenda.</span><span class="sxs-lookup"><span data-stu-id="7aa87-106">Likewise, you can schedule a Lync Server conference from within Microsoft SharePoint Server; again, however, this can only be done if the two servers (SharePoint and Lync Server) trust one another.</span></span> <span data-ttu-id="7aa87-107">Anche se è possibile usare un meccanismo di autenticazione per la comunicazione Lync-to-Exchange e un meccanismo separato per la comunicazione da Lync a SharePoint, un approccio migliore e più efficiente consiste nell'usare un metodo standardizzato per tutti i server a server autenticazione e autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="7aa87-107">Although it's possible to use one authentication mechanism for Lync-to-Exchange communication and a separate mechanism for Lync-to-SharePoint communication, a better and more efficient approach is to use a standardized method for all server-to-server authentication and authorization.</span></span>

<span data-ttu-id="7aa87-108">L'approccio adottato da Lync Server 2013 è l'uso di un singolo metodo standardizzato per l'autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="7aa87-108">Using a single, standardized method for server-to-server authentication is the approach taken by Lync Server 2013.</span></span> <span data-ttu-id="7aa87-109">Per la versione di 2013, Lync Server 2013, oltre ad altri prodotti Microsoft Server, inclusi Exchange 2013 e Microsoft SharePoint Server, supporta il protocollo OAuth (Open Authorization) per l'autenticazione e l'autorizzazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="7aa87-109">For the 2013 release, Lync Server 2013 (as well as other Microsoft Server products, including Exchange 2013 and Microsoft SharePoint Server) support the OAuth (Open Authorization) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="7aa87-110">Con OAuth, un protocollo di autorizzazione standard usato da numerosi siti Web principali, le credenziali utente e le password non vengono passate da un computer a un altro.</span><span class="sxs-lookup"><span data-stu-id="7aa87-110">With OAuth, a standard authorization protocol used by a number of major websites, user credentials and passwords are not passed from one computer to another.</span></span> <span data-ttu-id="7aa87-111">L'autenticazione e l'autorizzazione si basano invece sullo scambio di token di sicurezza. questi token concedono l'accesso a un set di risorse specifico per un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="7aa87-111">Instead, authentication and authorization is based on the exchange of security tokens; these tokens grant access to a specific set of resources for a specific amount of time.</span></span>

<span data-ttu-id="7aa87-112">L'autenticazione OAuth include in genere tre parti: un singolo server di autorizzazione e i due ambiti che devono comunicare tra loro.</span><span class="sxs-lookup"><span data-stu-id="7aa87-112">OAuth authentication typically involves three parties: a single authorization server and the two realms that need to communicate with one another.</span></span> <span data-ttu-id="7aa87-113">È anche possibile eseguire l'autenticazione da server a server senza usare un server di autorizzazione, un processo che verrà illustrato più avanti in questo documento. I token di sicurezza vengono emessi dal server di autorizzazioni (noto anche come server token di sicurezza) ai due ambiti che devono comunicare. questi token verificano che le comunicazioni provenienti da un reame debbano essere considerate attendibili dall'altro Realm.</span><span class="sxs-lookup"><span data-stu-id="7aa87-113">(You can also do server-to-server authentication without using an authorization server, a process that will be discussed later in this document.) Security tokens are issued by the authorization server (also known as a security token server) to the two realms that need to communicate; these tokens verify that communications originating from one realm should be trusted by the other realm.</span></span> <span data-ttu-id="7aa87-114">Ad esempio, il server di autorizzazione può emettere token che verificano che gli utenti di un reame specifico di Lync Server 2013 siano in grado di accedere a un'area di autenticazione di Exchange 2013 specificata e viceversa.</span><span class="sxs-lookup"><span data-stu-id="7aa87-114">For example, the authorization server might issue tokens that verify that users from a specific Lync Server 2013 realm are able to access a specified Exchange 2013 realm, and vice-versa.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="7aa87-115">Un Realm è semplicemente un contenitore di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7aa87-115">A realm is simply a security container.</span></span> <span data-ttu-id="7aa87-116">Per impostazione predefinita, Lync Server 2013 usa il dominio SIP predefinito come area di autenticazione OAuth.</span><span class="sxs-lookup"><span data-stu-id="7aa87-116">By default, Lync Server 2013 uses your default SIP domain as its OAuth realm.</span></span> <span data-ttu-id="7aa87-117">Gli spazi dei nomi SIP aggiuntivi vengono aggiunti all'elenco nome alternativo oggetto nel certificato OAuth.</span><span class="sxs-lookup"><span data-stu-id="7aa87-117">Additional SIP namespaces are added to the Subject Alternate Name list in the OAuth certificate.</span></span>



</div>

<span data-ttu-id="7aa87-118">Lync Server 2013 supporta tre scenari di autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="7aa87-118">Lync Server 2013 supports three server-to-server authentication scenarios.</span></span> <span data-ttu-id="7aa87-119">Con Lync Server 2013 è possibile:</span><span class="sxs-lookup"><span data-stu-id="7aa87-119">With Lync Server 2013 you can:</span></span>

  - <span data-ttu-id="7aa87-120">Configurare l'autenticazione da server a server tra un'installazione locale di Lync Server 2013 e un'installazione locale di Exchange 2013 e/o Microsoft SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="7aa87-120">Configure server-to-server authentication between an on-premise installation of Lync Server 2013 and an on-premises installation of Exchange 2013 and/or Microsoft SharePoint Server.</span></span>

  - <span data-ttu-id="7aa87-121">Configurare l'autenticazione da server a server tra una coppia di componenti di Office 365, ad esempio tra Microsoft Exchange e Microsoft Lync Server o tra Microsoft Lync Server e Microsoft SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7aa87-121">Configure server-to-server authentication between a pair of Office 365 components (for example, between Microsoft Exchange and Microsoft Lync Server, or between Microsoft Lync Server and Microsoft SharePoint).</span></span>

  - <span data-ttu-id="7aa87-122">Configurare l'autenticazione da server a server in un ambiente interlocale, ovvero l'autenticazione da server a server tra un server locale e un componente di Office 365.</span><span class="sxs-lookup"><span data-stu-id="7aa87-122">Configure server-to-server authentication in a cross-premises environment (that is, server-to-server authentication between an on-premises server and an Office 365 component).</span></span>

<span data-ttu-id="7aa87-123">Tieni presente che, in questo momento, solo Exchange 2013, SharePoint Server e Lync Server 2013 supportano l'autenticazione da server a server; Se non si esegue uno di questi server, non sarà possibile implementare completamente l'autenticazione OAuth.</span><span class="sxs-lookup"><span data-stu-id="7aa87-123">Note that, at this point in time, only Exchange 2013, SharePoint Server, and Lync Server 2013 support server-to-server authentication; if you are not running one of these servers then you will not be able to fully implement OAuth authentication.</span></span>

<span data-ttu-id="7aa87-124">Occorre anche sottolineare che non è necessario usare l'autenticazione da server a server: non è necessaria l'autenticazione da server a server per distribuire Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7aa87-124">It should also be pointed out that you do not need to use server-to-server authentication: server-to-server authentication is not required in order to deploy Lync Server 2013.</span></span> <span data-ttu-id="7aa87-125">Se Lync Server 2013 non deve comunicare con altri server, ad esempio Exchange 2013, non è necessaria l'autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="7aa87-125">If Lync Server 2013 does not need to communicate with other servers (such as Exchange 2013) then server-to-server authentication is not needed.</span></span>

<span data-ttu-id="7aa87-126">Tuttavia, è necessaria l'autenticazione da server a server se si vogliono usare alcune delle nuove funzionalità di Lync Server, come l'"archivio contatti unificato".</span><span class="sxs-lookup"><span data-stu-id="7aa87-126">However, server-to-server authentication is required if you want to use some of Lync Server's new features, such as the "unified contact store."</span></span> <span data-ttu-id="7aa87-127">Con l'archivio contatti unificato, le informazioni di contatto di Lync Server 2013 sono archiviate in Exchange 2013 anziché in Lync Server; Ciò consente agli utenti di avere un singolo set di contatti facilmente accessibile dall'interno di Lync, Microsoft Outlook o Microsoft Outlook Web Access.</span><span class="sxs-lookup"><span data-stu-id="7aa87-127">With unified contact store, Lync Server 2013 contact information is stored in Exchange 2013 instead of in Lync Server; this enables users to have a single set of contacts that is readily accessible from within Lync, Microsoft Outlook, or Microsoft Outlook Web Access.</span></span> <span data-ttu-id="7aa87-128">Poiché l'archivio contatti unificato richiede Lync Server 2013 per condividere informazioni con Exchange 2013, è necessario usare l'autenticazione da server a server per distribuire la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7aa87-128">Because the unified contact store requires Lync Server 2013 to share information with Exchange 2013, you must use server-to-server authentication in order to deploy the feature.</span></span> <span data-ttu-id="7aa87-129">È necessaria anche l'autenticazione da server a server se si sceglie di usare l'archiviazione di Exchange, in cui le trascrizioni delle sessioni di messaggistica istantanea vengono salvate come messaggi di posta elettronica di Exchange 2013 anziché come singoli record di database.</span><span class="sxs-lookup"><span data-stu-id="7aa87-129">Server-to-server authentication is also required if you choose to use Exchange archiving, in which the transcripts of instant messaging sessions are saved as Exchange 2013 emails rather than as individual database records.</span></span>

<span data-ttu-id="7aa87-130">Per la versione di Office 365 di Lync Server per comunicare con la controparte di Exchange, Lync Server 2013 deve prima ottenere un token di sicurezza dal server di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="7aa87-130">For the Office 365 version of Lync Server to communicate with its Exchange counterpart, Lync Server 2013 must first obtain a security token from the authorization server.</span></span> <span data-ttu-id="7aa87-131">Lync Server usa quindi il token di sicurezza per identificarsi in Exchange.</span><span class="sxs-lookup"><span data-stu-id="7aa87-131">Lync Server then uses that security token to identify itself to Exchange.</span></span> <span data-ttu-id="7aa87-132">La versione di Exchange di Office 365 deve passare allo stesso processo per comunicare con Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7aa87-132">The Office 365 version of Exchange must go through the same process in order to communicate with Lync Server 2013.</span></span>

<span data-ttu-id="7aa87-133">Tuttavia, per l'autenticazione da server a server locale tra due server Microsoft non è necessario usare un server di token di terze parti.</span><span class="sxs-lookup"><span data-stu-id="7aa87-133">However, for on-premises server-to-server authentication between two Microsoft servers there is no need to use a third-party token server.</span></span> <span data-ttu-id="7aa87-134">I prodotti server, ad esempio Lync Server 2013 ed Exchange 2013, hanno un server token incorporato che può essere usato per scopi di autenticazione con altri server Microsoft, ad esempio SharePoint Server, che supportano l'autenticazione da server a server.</span><span class="sxs-lookup"><span data-stu-id="7aa87-134">Server products such as Lync Server 2013 and Exchange 2013 have a built-in token server that can be used for authentication purposes with other Microsoft servers (such as SharePoint server) that support server-to-server authentication.</span></span> <span data-ttu-id="7aa87-135">Ad esempio, Lync Server 2013 può emettere e firmare un token di sicurezza da solo, quindi usare il token per comunicare con Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="7aa87-135">For example, Lync Server 2013 can issue and sign a security token by itself, then use that token to communicate with Exchange 2013.</span></span> <span data-ttu-id="7aa87-136">In un caso come questo, non è necessario un server di token di terze parti.</span><span class="sxs-lookup"><span data-stu-id="7aa87-136">In a case like this, there is no need for a third-party token server.</span></span>

<span data-ttu-id="7aa87-137">Per configurare l'autenticazione da server a server per un'implementazione locale di Lync Server 2013, è necessario eseguire due operazioni:</span><span class="sxs-lookup"><span data-stu-id="7aa87-137">In order to configure server-to-server authentication for an on-premises implementation of Lync Server 2013 you must do two things:</span></span>

  - <span data-ttu-id="7aa87-138">Assegnare un certificato all'autorità di certificazione predefinita del token di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7aa87-138">Assign a certificate to Lync Server's built-in token issuer.</span></span>

  - <span data-ttu-id="7aa87-139">Configurare il server con cui Lync Server 2013 comunicherà come "applicazione partner".</span><span class="sxs-lookup"><span data-stu-id="7aa87-139">Configure the server that Lync Server 2013 will communicate with to be a "partner application."</span></span> <span data-ttu-id="7aa87-140">Se ad esempio Lync Server 2013 deve comunicare con Exchange 2013, sarà necessario configurare Exchange in modo che sia un'applicazione partner.</span><span class="sxs-lookup"><span data-stu-id="7aa87-140">For example, if Lync Server 2013 needs to communicate with Exchange 2013 then you will need to configure Exchange to be a partner application.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="7aa87-141">Un'applicazione partner è un'applicazione in cui Lync Server 2013 può scambiare direttamente i token di sicurezza, senza dover passare a un server token di sicurezza di terze parti.</span><span class="sxs-lookup"><span data-stu-id="7aa87-141">A "partner application" is any application that Lync Server 2013 can directly exchange security tokens with, without having to go through a third-party security token server.</span></span>



</div>

<span data-ttu-id="7aa87-142">Tieni presente che OAuth è una parte centrale del prodotto e non può essere disabilitato o rimosso.</span><span class="sxs-lookup"><span data-stu-id="7aa87-142">Note that OAuth is a core part of the product and cannot be disabled or removed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="7aa87-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7aa87-143">See Also</span></span>


[<span data-ttu-id="7aa87-144">Assegnazione di un certificato di autenticazione da server a server a Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7aa87-144">Assigning a server-to-server authentication certificate to Microsoft Lync Server 2013</span></span>](lync-server-2013-assigning-a-server-to-server-authentication-certificate-to-lync-server-2013.md)  
[<span data-ttu-id="7aa87-145">Configurazione di Microsoft Lync Server 2013 in un ambiente tra più locali</span><span class="sxs-lookup"><span data-stu-id="7aa87-145">Configuring Microsoft Lync Server 2013 in a cross-premises environment</span></span>](lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

