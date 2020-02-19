---
title: 'Lync Server 2013: attività di distribuzione per il controllo delle chiamate remote'
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
ms.openlocfilehash: d1549cb2f71e5f6f0ab1d16907d5e83765780cca
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-tasks-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="459b0-102">Attività di distribuzione per il controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="459b0-102">Deployment tasks for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="459b0-103">_**Ultimo argomento modificato:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="459b0-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="459b0-104">In questo argomento vengono descritte le attività di distribuzione che è necessario eseguire per abilitare il controllo delle chiamate remote per gli utenti nell'ambiente di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="459b0-104">This topic describes the deployment tasks that you must perform to enable remote call control for users in your Lync Server environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="459b0-105">Se si esegue la migrazione degli utenti precedentemente abilitati per il controllo delle chiamate remote in Microsoft Office Communicator 2007 R2, è necessario eseguire un'attività di distribuzione aggiuntiva prima di iniziare a eseguire le attività di distribuzione del controllo delle chiamate remote descritte in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="459b0-105">If you are migrating users previously enabled for remote call control in Microsoft Office Communicator 2007 R2, you must perform an additional deployment task before you begin performing the remote call control deployment tasks described in this topic.</span></span> <span data-ttu-id="459b0-106">Durante il processo di migrazione a Lync Server, è necessario rimuovere le voci di applicazioni attendibili (in precedenza note come <EM>voci host autorizzate</EM>) utilizzando gli strumenti di amministrazione di Office Communications Server 2007 R2, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="459b0-106">During the migration process to Lync Server, trusted application entries (previously known as <EM>authorized host entries</EM>) must be removed by using the Office Communications Server 2007 R2 administrative tools, as appropriate.</span></span><BR><span data-ttu-id="459b0-107">Per informazioni dettagliate sulla rimozione di host autorizzati, vedere <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a Legacy Authorized host in Lync Server 2013 (optional)</A>.</span><span class="sxs-lookup"><span data-stu-id="459b0-107">For details about removing authorized hosts, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span>



</div>

<div>

## <a name="step-1-install-and-configure-the-sipcsta-gateway-to-communicate-with-your-pbx"></a><span data-ttu-id="459b0-108">Passaggio 1: installare e configurare il gateway SIP/CSTA per comunicare con un PBX</span><span class="sxs-lookup"><span data-stu-id="459b0-108">Step 1: Install and Configure the SIP/CSTA Gateway to Communicate with Your PBX</span></span>

<span data-ttu-id="459b0-109">È necessario installare almeno un gateway SIP/CSTA che sia in grado di connettersi a Lync Server e al PBX (Private Branch Exchange) esistente nel proprio ambiente per fornire agli utenti le funzionalità di controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="459b0-109">You need to install at least one SIP/CSTA gateway that can connect to both Lync Server and the existing private branch exchange (PBX) in your environment in order to provide remote call control features to your users.</span></span> <span data-ttu-id="459b0-110">Un gateway SIP/CSTA è un gateway tra SIP e CSTA (Computer-Supported Telecommunications Application).</span><span class="sxs-lookup"><span data-stu-id="459b0-110">A SIP/CSTA gateway is a gateway between SIP and a computer-supported telecommunications application (CSTA).</span></span> <span data-ttu-id="459b0-111">Indipendentemente dal numero di gateway installati, ogni utente può essere configurato con un solo gateway o PBX.</span><span class="sxs-lookup"><span data-stu-id="459b0-111">Whether you install multiple gateways or just one, each user can be configured with only one gateway or PBX.</span></span> <span data-ttu-id="459b0-112">Se il PBX esistente non dispone di un'interfaccia SIP/CSTA, distribuire un gateway SIP/CSTA in grado di supportare il PBX, incluso il supporto per protocolli di segnalazione specifici del fornitore del PBX proprietario.</span><span class="sxs-lookup"><span data-stu-id="459b0-112">If your existing PBX does not have a SIP/CSTA interface, ensure you deploy a SIP/CSTA gateway that can support the PBX, including support for proprietary PBX vendor-specific signaling protocols.</span></span> <span data-ttu-id="459b0-113">Per informazioni dettagliate sulle funzionalità, rivolgersi direttamente al fornitore.</span><span class="sxs-lookup"><span data-stu-id="459b0-113">For details about capabilities, consult each vendor directly.</span></span>

<span data-ttu-id="459b0-114">Quando si è pronti a distribuire un gateway SIP/CSTA che può integrarsi con Lync Server per il controllo delle chiamate remote, consultare anche il fornitore del gateway o la documentazione relativa al gateway del fornitore per quanto riguarda la sintassi richiesta dal gateway per le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="459b0-114">When you are ready to deploy a SIP/CSTA gateway that can integrate with Lync Server for remote call control, also consult with your gateway vendor or the vendor’s gateway documentation regarding the syntax required by the gateway for the following information:</span></span>

  - <span data-ttu-id="459b0-115">URI server linea del gateway</span><span class="sxs-lookup"><span data-stu-id="459b0-115">Line server URI of the gateway</span></span>

  - <span data-ttu-id="459b0-116">URI di linea per gli utenti che verranno assegnati al gateway</span><span class="sxs-lookup"><span data-stu-id="459b0-116">Line URI for users that will be assigned to the gateway</span></span>

<span data-ttu-id="459b0-117">Le impostazioni precedenti sono necessarie durante la configurazione utente e devono essere specificate come previsto dal gateway per eseguire correttamente il routing e la connessione al PBX.</span><span class="sxs-lookup"><span data-stu-id="459b0-117">The preceding settings are required during user configuration and must be specified as expected by the gateway to route and connect to the PBX properly.</span></span>

<span data-ttu-id="459b0-118">È possibile fare riferimento ai fornitori nel sito Web Microsoft Unified Communications Open Interoperability Program all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309).</span><span class="sxs-lookup"><span data-stu-id="459b0-118">You can refer to vendors on the Microsoft Unified Communications Open Interoperability Program website at [https://go.microsoft.com/fwlink/p/?linkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

</div>

<div>

## <a name="step-2-configure-lync-server-to-route-csta-requests-to-the-sipcsta-gateway"></a><span data-ttu-id="459b0-119">Passaggio 2: configurare Lync Server per instradare le richieste CSTA al gateway SIP/CSTA</span><span class="sxs-lookup"><span data-stu-id="459b0-119">Step 2: Configure Lync Server to Route CSTA Requests to the SIP/CSTA Gateway</span></span>

<span data-ttu-id="459b0-120">È necessario creare route statiche nei pool di Lync Server con l'indirizzo di destinazione (URI server) di tutti i gateway SIP/CSTA nella distribuzione a cui si intende instradare le richieste di controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="459b0-120">You must create static routes on Lync Server pools to the destination address (server URI) of all SIP/CSTA gateways in your deployment to which you intend to route remote call control requests.</span></span> <span data-ttu-id="459b0-121">È inoltre necessario creare una voce di applicazione attendibile corrispondente a ogni indirizzo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="459b0-121">You must also create a trusted application entry that corresponds to each destination address.</span></span> <span data-ttu-id="459b0-122">Quando si designa il gateway come applicazione attendibile, viene assegnato lo stato attendibile all'esecuzione come parte dell'ambiente Lync Server anche se è stato sviluppato da terze parti (ed è in esecuzione ciò che viene definito come *servizio esterno* , poiché si tratta di un servizio che non è una parte incorporata del prodotto).</span><span class="sxs-lookup"><span data-stu-id="459b0-122">When you designate the gateway as a trusted application, it is given trusted status to run as part of the Lync Server environment even though it is developed by a third party (and runs what is referred to as an *external service* because it is a service that is not a built-in part of the product).</span></span> <span data-ttu-id="459b0-123">Infine, se Lync Server si connetterà al gateway SIP/CSTA utilizzando una connessione TCP (Transmission Control Protocol) anziché una connessione TLS (Transport Layer Security), è necessario definire anche l'indirizzo IP del gateway tramite Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="459b0-123">Finally, if Lync Server will connect to the SIP/CSTA gateway using a Transmission Control Protocol (TCP) connection instead of a Transport Layer Security (TLS) connection, you must also define the gateway IP address by using Topology Builder.</span></span>

<span data-ttu-id="459b0-124">Per informazioni dettagliate sulla configurazione delle route statiche, vedere [configurare una route statica per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="459b0-124">For details about configuring static routes, see [Configure a static route for remote call control in Lync Server 2013](lync-server-2013-configure-a-static-route-for-remote-call-control.md).</span></span>

<span data-ttu-id="459b0-125">Per informazioni dettagliate sulla configurazione di voci di applicazioni attendibili, vedere [Configure a Trusted Application Entry for Remote Call Control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="459b0-125">For details about configuring trusted application entries, see [Configure a trusted application entry for remote call control in Lync Server 2013](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md).</span></span>

<span data-ttu-id="459b0-126">Per informazioni dettagliate sulla definizione di un indirizzo IP del gateway SIP/CSTA in Generatore di topologie, vedere [define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span><span class="sxs-lookup"><span data-stu-id="459b0-126">For details about defining a SIP/CSTA gateway IP address in Topology Builder, see [Define a SIP/CSTA gateway IP address in Lync Server 2013](lync-server-2013-define-a-sip-csta-gateway-ip-address.md).</span></span>

</div>

<div>

## <a name="step-3-configure-lync-users-for-remote-call-control"></a><span data-ttu-id="459b0-127">Passaggio 3: configurare gli utenti di Lync per il controllo delle chiamate remote</span><span class="sxs-lookup"><span data-stu-id="459b0-127">Step 3: Configure Lync Users for Remote Call Control</span></span>

<span data-ttu-id="459b0-128">Dopo che gli utenti sono stati abilitati per Lync Server, è possibile utilizzare il pannello di controllo di Lync Server o Lync Server Management Shell per abilitare il controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="459b0-128">After users have been enabled for Lync Server, you can use Lync Server Control Panel or Lync Server Management Shell to enable them for remote call control.</span></span> <span data-ttu-id="459b0-129">Durante questo passaggio di distribuzione si assegna a ogni utente in URI server linea e un URI di linea.</span><span class="sxs-lookup"><span data-stu-id="459b0-129">It is during this deployment step that you assign each user a line server URI and a line URI.</span></span> <span data-ttu-id="459b0-130">L'URI server linea è l'URI SIP del gateway SIP/CSTA che si intende assegnare all'utente.</span><span class="sxs-lookup"><span data-stu-id="459b0-130">The line server URI is the SIP URI of the SIP/CSTA gateway that you plan to assign to the user.</span></span> <span data-ttu-id="459b0-131">L'URI di linea è il numero di telefono univoco assegnato all'utente.</span><span class="sxs-lookup"><span data-stu-id="459b0-131">The line URI is the unique phone number assigned to the user.</span></span>

<span data-ttu-id="459b0-132">Per informazioni dettagliate sulla configurazione degli utenti per il controllo delle chiamate remote, vedere [abilitare gli utenti di Lync per il controllo delle chiamate remote in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span><span class="sxs-lookup"><span data-stu-id="459b0-132">For details about configuring users for remote call control, see [Enable Lync users for remote call control in Lync Server 2013](lync-server-2013-enable-lync-users-for-remote-call-control.md).</span></span>

</div>

<div>

## <a name="step-4-define-the-lync-server-phone-number-normalization-rules"></a><span data-ttu-id="459b0-133">Passaggio 4: definire le regole di normalizzazione dei numeri di telefono di Lync Server</span><span class="sxs-lookup"><span data-stu-id="459b0-133">Step 4: Define the Lync Server Phone Number Normalization Rules</span></span>

<span data-ttu-id="459b0-134">Negli scenari di controllo delle chiamate remote, Lync Server utilizza le regole di normalizzazione dei numeri di telefono per convertire il numero di telefono ricevuto dal gateway SIP/CSTA nel formato E. 164.</span><span class="sxs-lookup"><span data-stu-id="459b0-134">In remote call control scenarios, Lync Server uses phone number normalization rules to convert phone numbers it receives from the SIP/CSTA gateway to E.164 format.</span></span> <span data-ttu-id="459b0-135">I numeri di telefono devono essere in questo formato standardizzato per garantire il corretto funzionamento di alcune funzionalità di controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="459b0-135">Phone numbers must be in this standardized format for certain remote call control features to function properly.</span></span> <span data-ttu-id="459b0-136">Il controllo delle chiamate remote utilizza le stesse regole di normalizzazione dei numeri di telefono configurate per la normalizzazione dei numeri di telefono del servizio Rubrica, che sono diverse da quelle utilizzate per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="459b0-136">Remote call control uses the same phone number normalization rules that you configure for Address Book Service phone number normalization, which are different from the phone number normalization rules used for Enterprise Voice.</span></span>

<span data-ttu-id="459b0-137">Per informazioni dettagliate su come il controllo delle chiamate remote utilizza le regole di normalizzazione dei numeri di telefono, vedere [Remote Call Control and Phone Number normalizzation in Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span><span class="sxs-lookup"><span data-stu-id="459b0-137">For details about how remote call control uses phone number normalization rules, see [Remote call control and phone number normalization in Lync Server 2013](lync-server-2013-remote-call-control-and-phone-number-normalization.md).</span></span> <span data-ttu-id="459b0-138">Per informazioni dettagliate sulle regole di normalizzazione dei numeri di telefono per il servizio Rubrica, vedere [Administering the Address Book Service in Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) topic nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="459b0-138">For details about phone number normalization rules for Address Book Service, see [Administering the Address Book Service in Lync Server 2013](lync-server-2013-administering-the-address-book-service.md) topic in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

