---
title: 'Lync Server 2013: Attività di distribuzione per il controllo delle chiamate remote'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment tasks for remote call control
ms:assetid: 20218871-4f27-4611-9b7e-c0ca55908284
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558624(v=OCS.15)
ms:contentKeyID: 48183599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df80ebcdc879598677a037d60c9eeeee46ba5209
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="41d35-102">Attività di distribuzione per il controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41d35-102">Deployment tasks for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41d35-103">_**Argomento Ultima modifica:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="41d35-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="41d35-104">In questo argomento vengono illustrate le attività di distribuzione che è necessario eseguire per abilitare il controllo delle chiamate remote per gli utenti nell'ambiente Lync Server.</span><span class="sxs-lookup"><span data-stu-id="41d35-104">This topic describes the deployment tasks that you must perform to enable remote call control for users in your Lync Server environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="41d35-105">Se si esegue la migrazione degli utenti precedentemente abilitati per il controllo delle chiamate remote in Microsoft Office Communicator 2007 R2, è necessario eseguire un'attività di distribuzione aggiuntiva prima di iniziare a eseguire le attività di distribuzione del controllo delle chiamate remote descritte in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="41d35-105">If you are migrating users previously enabled for remote call control in Microsoft Office Communicator 2007 R2, you must perform an additional deployment task before you begin performing the remote call control deployment tasks described in this topic.</span></span> <span data-ttu-id="41d35-106">Durante il processo di migrazione a Lync Server, le voci di applicazione attendibili (precedentemente note come <EM>voci dell'host autorizzato</EM>) devono essere rimosse usando gli strumenti amministrativi di Office Communications Server 2007 R2, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="41d35-106">During the migration process to Lync Server, trusted application entries (previously known as <EM>authorized host entries</EM>) must be removed by using the Office Communications Server 2007 R2 administrative tools, as appropriate.</span></span><BR><span data-ttu-id="41d35-107">Per informazioni dettagliate sulla rimozione di host autorizzati, vedere <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">rimuovere un host autorizzato legacy in Lync Server 2013 (facoltativo)</A>.</span><span class="sxs-lookup"><span data-stu-id="41d35-107">For details about removing authorized hosts, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span>



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a><span data-ttu-id="41d35-108">Passaggio 1: installare e configurare il gateway SIP/CSTA per comunicare con il PBX</span><span class="sxs-lookup"><span data-stu-id="41d35-108">Step 1: Install and Configure the SIP/CSTA Gateway to Communicate with Your PBX</span></span>

<span data-ttu-id="41d35-109">È necessario installare almeno un gateway SIP/CSTA in grado di connettersi sia a Lync Server che al PBX (Private Branch Exchange) esistente nell'ambiente per ottenere funzionalità di controllo delle chiamate remote agli utenti.</span><span class="sxs-lookup"><span data-stu-id="41d35-109">You need to install at least one SIP/CSTA gateway that can connect to both Lync Server and the existing private branch exchange (PBX) in your environment in order to provide remote call control features to your users.</span></span> <span data-ttu-id="41d35-110">Un gateway SIP/CSTA è un gateway tra SIP e un'applicazione di telecomunicazioni supportata dal computer (CSTA).</span><span class="sxs-lookup"><span data-stu-id="41d35-110">A SIP/CSTA gateway is a gateway between SIP and a computer-supported telecommunications application (CSTA).</span></span> <span data-ttu-id="41d35-111">Indipendentemente dal fatto che si installino più gateway o uno solo, ogni utente può essere configurato con un solo gateway o PBX.</span><span class="sxs-lookup"><span data-stu-id="41d35-111">Whether you install multiple gateways or just one, each user can be configured with only one gateway or PBX.</span></span> <span data-ttu-id="41d35-112">Se il tuo PBX esistente non ha un'interfaccia SIP/CSTA, assicurati di distribuire un gateway SIP/CSTA in grado di supportare il PBX, incluso il supporto per i protocolli di segnalazione specifici del fornitore PBX.</span><span class="sxs-lookup"><span data-stu-id="41d35-112">If your existing PBX does not have a SIP/CSTA interface, ensure you deploy a SIP/CSTA gateway that can support the PBX, including support for proprietary PBX vendor-specific signaling protocols.</span></span> <span data-ttu-id="41d35-113">Per informazioni dettagliate sulle funzionalità, consultare direttamente ogni fornitore.</span><span class="sxs-lookup"><span data-stu-id="41d35-113">For details about capabilities, consult each vendor directly.</span></span>

<span data-ttu-id="41d35-114">Quando si è pronti a distribuire un gateway SIP/CSTA che può essere integrato con Lync Server per il controllo delle chiamate remote, consultare anche il fornitore del gateway o la documentazione del gateway del fornitore relativa alla sintassi richiesta dal gateway per le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="41d35-114">When you are ready to deploy a SIP/CSTA gateway that can integrate with Lync Server for remote call control, also consult with your gateway vendor or the vendor’s gateway documentation regarding the syntax required by the gateway for the following information:</span></span>

  - <span data-ttu-id="41d35-115">URI del server di linea del gateway</span><span class="sxs-lookup"><span data-stu-id="41d35-115">Line server URI of the gateway</span></span>

  - <span data-ttu-id="41d35-116">URI di linea per gli utenti che verranno assegnati al gateway</span><span class="sxs-lookup"><span data-stu-id="41d35-116">Line URI for users that will be assigned to the gateway</span></span>

<span data-ttu-id="41d35-117">Le impostazioni precedenti sono necessarie durante la configurazione dell'utente e devono essere specificate come previsto dal gateway per instradare e connettere correttamente il PBX.</span><span class="sxs-lookup"><span data-stu-id="41d35-117">The preceding settings are required during user configuration and must be specified as expected by the gateway to route and connect to the PBX properly.</span></span>

<span data-ttu-id="41d35-118">È possibile fare riferimento a fornitori nel sito Web Microsoft Unified Communications Open Interoperability Program [http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).</span><span class="sxs-lookup"><span data-stu-id="41d35-118">You can refer to vendors on the Microsoft Unified Communications Open Interoperability Program website at [http://go.microsoft.com/fwlink/p/?linkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a><span data-ttu-id="41d35-119">Passaggio 2: configurare Lync Server per instradare le richieste CSTA al gateway SIP/CSTA</span><span class="sxs-lookup"><span data-stu-id="41d35-119">Step 2: Configure Lync Server to Route CSTA Requests to the SIP/CSTA Gateway</span></span>

<span data-ttu-id="41d35-120">È necessario creare route statiche nei pool di Lync Server fino all'indirizzo di destinazione (URI del server) di tutti i gateway SIP/CSTA nella distribuzione a cui si vuole instradare le richieste di controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="41d35-120">You must create static routes on Lync Server pools to the destination address (server URI) of all SIP/CSTA gateways in your deployment to which you intend to route remote call control requests.</span></span> <span data-ttu-id="41d35-121">Devi anche creare una voce di applicazione attendibile che corrisponda a ogni indirizzo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="41d35-121">You must also create a trusted application entry that corresponds to each destination address.</span></span> <span data-ttu-id="41d35-122">Quando si designa il gateway come applicazione attendibile, viene assegnato lo stato attendibile per l'esecuzione come parte dell'ambiente Lync Server anche se è sviluppato da una terza parte (ed esegue il nome di un *servizio esterno* perché si tratta di un servizio che non è una parte incorporata del prodotto).</span><span class="sxs-lookup"><span data-stu-id="41d35-122">When you designate the gateway as a trusted application, it is given trusted status to run as part of the Lync Server environment even though it is developed by a third party (and runs what is referred to as an *external service* because it is a service that is not a built-in part of the product).</span></span> <span data-ttu-id="41d35-123">Infine, se Lync Server si connette al gateway SIP/CSTA usando una connessione TCP (Transmission Control Protocol) invece di una connessione TLS (Transport Layer Security), è necessario definire anche l'indirizzo IP del gateway usando generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="41d35-123">Finally, if Lync Server will connect to the SIP/CSTA gateway using a Transmission Control Protocol (TCP) connection instead of a Transport Layer Security (TLS) connection, you must also define the gateway IP address by using Topology Builder.</span></span>

<span data-ttu-id="41d35-124">Per informazioni dettagliate sulla configurazione di route statiche, vedere [configurare una route statica per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="41d35-124">For details about configuring static routes, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span></span>

<span data-ttu-id="41d35-125">Per informazioni dettagliate sulla configurazione di voci di applicazione attendibili, vedere [configurare una voce di applicazione attendibile per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="41d35-125">For details about configuring trusted application entries, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span></span>

<span data-ttu-id="41d35-126">Per informazioni dettagliate sulla definizione di un indirizzo IP del gateway SIP/CSTA in Generatore di topologia, vedere [definire un indirizzo IP del gateway SIP/CSTA in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span><span class="sxs-lookup"><span data-stu-id="41d35-126">For details about defining a SIP/CSTA gateway IP address in Topology Builder, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span></span>

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a><span data-ttu-id="41d35-127">Passaggio 3: configurare gli utenti di Lync per il controllo delle chiamate remote</span><span class="sxs-lookup"><span data-stu-id="41d35-127">Step 3: Configure Lync Users for Remote Call Control</span></span>

<span data-ttu-id="41d35-128">Dopo che gli utenti sono stati abilitati per Lync Server, è possibile usare il pannello di controllo di Lync Server o Lync Server Management Shell per abilitarli per il controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="41d35-128">After users have been enabled for Lync Server, you can use Lync Server Control Panel or Lync Server Management Shell to enable them for remote call control.</span></span> <span data-ttu-id="41d35-129">È durante questo passaggio di distribuzione che si assegna a ogni utente un URI del server di linea e un URI di linea.</span><span class="sxs-lookup"><span data-stu-id="41d35-129">It is during this deployment step that you assign each user a line server URI and a line URI.</span></span> <span data-ttu-id="41d35-130">L'URI del server di linea è l'URI SIP del gateway SIP/CSTA che si prevede di assegnare all'utente.</span><span class="sxs-lookup"><span data-stu-id="41d35-130">The line server URI is the SIP URI of the SIP/CSTA gateway that you plan to assign to the user.</span></span> <span data-ttu-id="41d35-131">L'URI di linea è il numero di telefono univoco assegnato all'utente.</span><span class="sxs-lookup"><span data-stu-id="41d35-131">The line URI is the unique phone number assigned to the user.</span></span>

<span data-ttu-id="41d35-132">Per informazioni dettagliate sulla configurazione degli utenti per il controllo delle chiamate remote, vedere [abilitare gli utenti di Lync per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="41d35-132">For details about configuring users for remote call control, see [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a><span data-ttu-id="41d35-133">Passaggio 4: definire le regole di normalizzazione dei numeri di telefono di Lync Server</span><span class="sxs-lookup"><span data-stu-id="41d35-133">Step 4: Define the Lync Server Phone Number Normalization Rules</span></span>

<span data-ttu-id="41d35-134">Negli scenari di controllo delle chiamate remote, Lync Server usa le regole di normalizzazione dei numeri di telefono per convertire il numero di telefono ricevuto dal gateway SIP/CSTA al formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="41d35-134">In remote call control scenarios, Lync Server uses phone number normalization rules to convert phone numbers it receives from the SIP/CSTA gateway to E.164 format.</span></span> <span data-ttu-id="41d35-135">I numeri di telefono devono essere in questo formato standardizzato per alcune funzionalità di controllo delle chiamate remote per funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="41d35-135">Phone numbers must be in this standardized format for certain remote call control features to function properly.</span></span> <span data-ttu-id="41d35-136">Il controllo delle chiamate remote usa le stesse regole di normalizzazione dei numeri di telefono configurate per la normalizzazione dei numeri di telefono del servizio Rubrica, che sono diversi dalle regole di normalizzazione dei numeri di telefono usate per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="41d35-136">Remote call control uses the same phone number normalization rules that you configure for Address Book Service phone number normalization, which are different from the phone number normalization rules used for Enterprise Voice.</span></span>

<span data-ttu-id="41d35-137">Per informazioni dettagliate su come il controllo delle chiamate remote USA regole di normalizzazione dei numeri di telefono, vedere [controllo delle chiamate remote e normalizzazione di numeri di telefono in Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span><span class="sxs-lookup"><span data-stu-id="41d35-137">For details about how remote call control uses phone number normalization rules, see [Remote call control and phone number normalization in Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span></span> <span data-ttu-id="41d35-138">Per informazioni dettagliate sulle regole di normalizzazione dei numeri di telefono per il servizio Rubrica, vedere [amministrazione del servizio Rubrica in Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) argomento della documentazione delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="41d35-138">For details about phone number normalization rules for Address Book Service, see [Administering the Address Book Service in Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) topic in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

