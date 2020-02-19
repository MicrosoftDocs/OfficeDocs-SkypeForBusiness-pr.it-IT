---
title: "Lync Server 2013: informazioni sull'individuazione automatica"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 033f3a12ccbe0817f586aa7eb868679fa44541fd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a><span data-ttu-id="79705-102">Informazioni su individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79705-102">Understanding Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79705-103">_**Ultimo argomento modificato:** 2013-06-03_</span><span class="sxs-lookup"><span data-stu-id="79705-103">_**Topic Last Modified:** 2013-06-03_</span></span>

<span data-ttu-id="79705-104">Il servizio di individuazione automatica di Lync Server 2013 è una funzionalità originariamente introdotta in Microsoft Lync Server 2010 come parte dell'aggiornamento cumulativo per Lync Server 2010: novembre 2011.</span><span class="sxs-lookup"><span data-stu-id="79705-104">The Lync Server 2013 Autodiscover Service is a feature that was originally introduced in Microsoft Lync Server 2010 as part of the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="79705-105">Oltre alle correzioni, questo aggiornamento cumulativo ha fornito il supporto per i client Lync mobile e Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="79705-105">In addition to fixes, this cumulative update delivered support for Lync Mobile and Lync 2013 clients.</span></span>

<span data-ttu-id="79705-106">In Lync Server 2013, il servizio di individuazione automatica è parte integrante del funzionamento dei client mobili esterni e interni e viene esteso anche ai nuovi client, ad esempio l'app Lync Windows Store recentemente introdotta per Windows 8.</span><span class="sxs-lookup"><span data-stu-id="79705-106">In Lync Server 2013, the Autodiscover Service is an integral part of the operation of external and internal mobile clients, and Autodiscover is also extended to new clients, such as the recently introduced Lync Windows Store app for Windows 8.</span></span> <span data-ttu-id="79705-107">L'individuazione automatica viene utilizzata anche dai client desktop Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="79705-107">Autodiscover is also used by the Lync 2013 desktop clients.</span></span> <span data-ttu-id="79705-108">Il servizio di individuazione automatica è riconosciuto in Lync Server dai record DNS (Domain Name System) necessari \*\*lyncdiscover.\< Domain\> \*\* e **LyncdiscoverInternal.\< dominio\>**.</span><span class="sxs-lookup"><span data-stu-id="79705-108">Autodiscover is recognized in Lync Server by the required domain name system (DNS) records **lyncdiscover.\<domain\>** and **lyncdiscoverinternal.\<domain\>**.</span></span> <span data-ttu-id="79705-109">Inoltre, le versioni più recenti di Lync 2010 e Lync 2013 desktop client preferiscono l'individuazione automatica sui record SRV DNS (Domain Name System), utilizzando i record DNS SRV solo se lyncdiscover. \<domain\> o LyncdiscoverInternal. \<il\> dominio non risponde o non si risolve.</span><span class="sxs-lookup"><span data-stu-id="79705-109">Additionally, newer versions of the Lync 2010 and Lync 2013 desktop client prefer Autodiscover over the domain name system (DNS) SRV records, using DNS SRV records only if lyncdiscover.\<domain\> or lyncdiscoverinternal.\<domain\> does not respond or does not resolve.</span></span> <span data-ttu-id="79705-110">L'app Lync Windows Store per Windows 8 e Lync mobile utilizza l'individuazione automatica esclusivamente e non si riferisce ai record DNS SRV tradizionali.</span><span class="sxs-lookup"><span data-stu-id="79705-110">The Lync Windows Store app for Windows 8 and Lync Mobile uses Autodiscover exclusively and will not refer to the traditional DNS SRV records.</span></span>

<span data-ttu-id="79705-111">In Lync Server 2013, l'individuazione automatica viene espansa per comunicare al client quali elementi, caratteristiche e metodi di comunicazione sono disponibili per il client.</span><span class="sxs-lookup"><span data-stu-id="79705-111">In Lync Server 2013, Autodiscover is expanded to communicate to the client which elements, features, and communication methods are available to the client.</span></span> <span data-ttu-id="79705-112">Le informazioni vengono comunicate tramite una richiesta inviata dal client e i servizi Web di Lync Server rispondono con una risposta chiaramente definita che consente di assegnare un nome a ciò che è disponibile per il client e come contattare tali funzionalità nel formato dell'individuazione automatica. Documento di risposta.</span><span class="sxs-lookup"><span data-stu-id="79705-112">The information is communicated through a request that is sent from the client, and the Lync Server web services responds with a clearly defined response that names what is available to the client, and how to contact those features in the format of the Autodiscover Response document.</span></span>

<span data-ttu-id="79705-113">Il modo migliore per comprendere il documento di risposta di individuazione automatica, compreso il modo in cui i servizi Web comunicano le caratteristiche ai client tramite questo documento, consiste nel sezionare e definire ogni riga in una risposta tipica del documento di risposta di individuazione automatica del servizio Web Lync.</span><span class="sxs-lookup"><span data-stu-id="79705-113">The best way to understand the Autodiscover response document, including how the web services communicate features to clients through this document, is to dissect and define each line in a typical response from the Lync web service Autodiscover response document.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="79705-114">Nei dettagli seguenti, l'utente ha già autenticato il server principale rispondendo a una richiesta di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="79705-114">In the details that follow, the user has already authenticated to the home server by responding to an authentication request.</span></span>



</div>

<div class="">


> [!NOTE]  
> <span data-ttu-id="79705-115">Il servizio Web di individuazione automatica di Lync è definito nei <STRONG>protocolli di Microsoft Office</STRONG> nella sezione <STRONG>Open specifiche</STRONG> della raccolta MSDN ( <STRONG>Microsoft Developer Network</STRONG> ).</span><span class="sxs-lookup"><span data-stu-id="79705-115">The Lync Autodiscover Web Service is defined in the <STRONG>Microsoft Office Protocols</STRONG> in the <STRONG>Open Specifications</STRONG> section of the <STRONG>Microsoft Developer Network</STRONG> (MSDN) library.</span></span> <span data-ttu-id="79705-116">Per informazioni dettagliate, vedere il documento delle specifiche complete, "Lync Autodiscover Web Service Protocol" all' <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A>Indirizzo:.</span><span class="sxs-lookup"><span data-stu-id="79705-116">For details, see the full specification document, "Lync Autodiscover Web Service Protocol," at: <A href="https://go.microsoft.com/fwlink/?linkid=273839">https://go.microsoft.com/fwlink/?LinkId=273839</A>.</span></span> <span data-ttu-id="79705-117">Per informazioni dettagliate sull'autenticazione, vedere "OC Authentication Web Service Protocol" <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A>all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="79705-117">For details about authentication, see "OC Authentication Web Service Protocol" at <A href="https://go.microsoft.com/fwlink/?linkid=279015">https://go.microsoft.com/fwlink/?LinkId=279015</A>.</span></span>



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a><span data-ttu-id="79705-118">Risposta di individuazione automatica del servizio Web di Lync Server</span><span class="sxs-lookup"><span data-stu-id="79705-118">The Lync Server Web Service Autodiscover Response</span></span>

<span data-ttu-id="79705-119">La risposta restituita quando viene inviata la richiesta di individuazione automatica è la stessa per un client interno o esterno.</span><span class="sxs-lookup"><span data-stu-id="79705-119">The response returned when the Autodiscover request is sent is the same for an internal or an external client.</span></span> <span data-ttu-id="79705-120">Alcuni parametri che possono essere modificati per la posizione potrebbero variare.</span><span class="sxs-lookup"><span data-stu-id="79705-120">Some parameters that are location–aware may change.</span></span> <span data-ttu-id="79705-121">Se viene ricevuta una richiesta del client, ma il pool effettivo è diverso da quello che è stato contattato, il pool di casa dell'utente verrà impostato per tale utente.</span><span class="sxs-lookup"><span data-stu-id="79705-121">If a client request is received, but the actual pool is other than the one that has been contacted, the user’s home pool will be set for that user.</span></span> <span data-ttu-id="79705-122">Un collega il cui account utente si trova in un pool diverso, ma accedendo dallo stesso ufficio, riceverà una risposta leggermente diversa.</span><span class="sxs-lookup"><span data-stu-id="79705-122">A colleague whose user account is on a different pool, but logging in from the same office, would get a slightly different response.</span></span> <span data-ttu-id="79705-123">La risposta indica il front end server o il pool Front end corretto per tale utente.</span><span class="sxs-lookup"><span data-stu-id="79705-123">The response indicates the correct Front End Server or Front End pool for that user.</span></span>

<span data-ttu-id="79705-124">Un esempio di un documento di risposta di individuazione automatica:</span><span class="sxs-lookup"><span data-stu-id="79705-124">An example of an Autodiscover Response document:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">
       <User>
          <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>
          <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>
          <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>
          <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>
          <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>
          <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>
          <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>
          <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>
          <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>
          <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>
          <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>
          <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>
          <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>
          <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>
          <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>
          <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>
       </User>
    </AutodiscoverResponse>

<div>

## <a name="autodiscover-response-document-details"></a><span data-ttu-id="79705-125">Dettagli del documento di risposta di individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="79705-125">Autodiscover Response Document Details</span></span>

<span data-ttu-id="79705-126">Il documento di risposta di individuazione automatica può essere in uno dei due formati.</span><span class="sxs-lookup"><span data-stu-id="79705-126">The Autodiscover Response document can be in one of two formats.</span></span> <span data-ttu-id="79705-127">Il formato predefinito è una notazione JSON (JavaScript Object Notation).</span><span class="sxs-lookup"><span data-stu-id="79705-127">The default format is a JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="79705-128">L'altro formato è un documento XML (Extensible Markup Language).</span><span class="sxs-lookup"><span data-stu-id="79705-128">The other format is extensible markup language (XML) document.</span></span> <span data-ttu-id="79705-129">Il codice XML viene utilizzato per questo esempio.</span><span class="sxs-lookup"><span data-stu-id="79705-129">The XML is used for this example.</span></span> <span data-ttu-id="79705-130">La richiesta e la risposta sono prevedibili perché il documento ha uno schema definito che determina il formato.</span><span class="sxs-lookup"><span data-stu-id="79705-130">The request and response are predictable because the document has a defined schema that determines the format.</span></span> <span data-ttu-id="79705-131">La riga del documento in cui viene descritto lo schema utilizzato è la prima riga della richiesta o della risposta:</span><span class="sxs-lookup"><span data-stu-id="79705-131">The line in the document that describes the schema used is the first line in the request or response:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

<span data-ttu-id="79705-132">La definizione di **AccessLocation = "External"** indica che la richiesta è stata effettuata da un utente esterno.</span><span class="sxs-lookup"><span data-stu-id="79705-132">The definition of **AccessLocation=”External”** indicates that the request was made from an external user.</span></span>

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

<span data-ttu-id="79705-133">SipServerInternalAccess e SipServerExternalAccess non sono attualmente utilizzati.</span><span class="sxs-lookup"><span data-stu-id="79705-133">SipServerInternalAccess and SipServerExternalAccess are currently not used.</span></span> <span data-ttu-id="79705-134">Tali voci sono riservate per un utilizzo futuro.</span><span class="sxs-lookup"><span data-stu-id="79705-134">These entries are reserved for future use.</span></span>

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

<span data-ttu-id="79705-135">SipClientInternalAccess e SipClientExternalAccess descrivono il nome di dominio completo e la porta che un client interno o esterno utilizzerà per accedere al server SIP definito.</span><span class="sxs-lookup"><span data-stu-id="79705-135">SipClientInternalAccess and SipClientExternalAccess describe the fully qualified domain name and port that an internal or external client will use to access the defined SIP Server.</span></span> <span data-ttu-id="79705-136">Il client Lync desktop e l'app Lync Windows Store utilizzano queste voci, in base alla posizione (interna o esterna) per individuare il server Director o front end.</span><span class="sxs-lookup"><span data-stu-id="79705-136">The Lync desktop client and the Lync Windows Store app use these entries, based on their location (internal or external) to find the Director or Front End Server.</span></span>

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

<span data-ttu-id="79705-137">I `Autodiscover` riferimenti contengono i punti di ingresso del servizio per il servizio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="79705-137">The `Autodiscover` references contain the service entry points for the Autodiscover service.</span></span> <span data-ttu-id="79705-138">L'attributo token contiene il nome del servizio e l'href è un URL che definisce per il client in cui è possibile trovare il servizio.</span><span class="sxs-lookup"><span data-stu-id="79705-138">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="79705-139">I client di una rete esterna utilizzano `External/Autodiscover`.</span><span class="sxs-lookup"><span data-stu-id="79705-139">Clients on an external network use the `External/Autodiscover`.</span></span> <span data-ttu-id="79705-140">Il servizio di individuazione automatica viene installato come parte del processo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="79705-140">The Autodiscover service is installed as part of the deployment process.</span></span> <span data-ttu-id="79705-141">`Internal/Autodiscover`non è attualmente utilizzato ed è riservato per utilizzi futuri.</span><span class="sxs-lookup"><span data-stu-id="79705-141">`Internal/Autodiscover` is not currently used, and is reserved for future use.</span></span>

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

<span data-ttu-id="79705-142">I `AuthBroker` riferimenti contengono i punti di ingresso del servizio per il servizio Broker di autenticazione interno e esterno, in questo caso SIP. svc.</span><span class="sxs-lookup"><span data-stu-id="79705-142">The `AuthBroker` references contain the service entry points for the internal and the external authentication broker service, in this case, sip.svc.</span></span> <span data-ttu-id="79705-143">L'attributo token contiene il nome del servizio e l'href è un URL che definisce per il client in cui è possibile trovare il servizio.</span><span class="sxs-lookup"><span data-stu-id="79705-143">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="79705-144">Client sulla rete interna con utilizzo `Internal/AuthBroker`.</span><span class="sxs-lookup"><span data-stu-id="79705-144">Clients on the internal network with use `Internal/AuthBroker`.</span></span> <span data-ttu-id="79705-145">I client di una rete esterna utilizzano `External/AuthBroker`.</span><span class="sxs-lookup"><span data-stu-id="79705-145">Clients on an external network use the `External/AuthBroker`.</span></span> <span data-ttu-id="79705-146">Il servizio AuthBroker viene installato come parte del processo di distribuzione dei servizi Web interni di distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79705-146">The AuthBroker service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

<span data-ttu-id="79705-147">Il `WebScheduler` token fa riferimento agli URL per l'accesso client alla programmazione basata sul Web per le conferenze di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="79705-147">The `WebScheduler` token references the URLs for client access to the web-based scheduling for Lync Server conferences.</span></span> <span data-ttu-id="79705-148">Attualmente, viene utilizzato `External/WebScheduler` solo il.</span><span class="sxs-lookup"><span data-stu-id="79705-148">Currently, only the `External/WebScheduler` is used.</span></span> <span data-ttu-id="79705-149">L'utilità Webscheduler è installata come parte del processo di distribuzione dei servizi Web di distribuzione di Lync Server 2013 interni.</span><span class="sxs-lookup"><span data-stu-id="79705-149">The WebScheduler is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

<span data-ttu-id="79705-150">`Internal/Mcx`e `External/Mcx` sono i percorsi dei servizi per dispositivi mobili, introdotti in aggiornamento cumulativo per Lync Server 2010: novembre 2011.</span><span class="sxs-lookup"><span data-stu-id="79705-150">`Internal/Mcx` and `External/Mcx` are the locations of the Mobility services, introduced in Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="79705-151">Tali riferimenti continueranno a essere utilizzati da Lync 2010 Mobile su tutti i dispositivi supportati.</span><span class="sxs-lookup"><span data-stu-id="79705-151">These references will continue to be used by Lync 2010 Mobile on all supported devices.</span></span> <span data-ttu-id="79705-152">Il servizio MCX viene installato come parte del processo di distribuzione dei servizi Web interni di distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79705-152">The Mcx service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

<span data-ttu-id="79705-153">**Internal/UCWA**, **External/UCWA** e **UCWA** forniscono un mezzo per consentire ai client di accedere all'interfaccia di programmazione delle applicazioni Web Unified Communications (UCWA API o Simply UCWA).</span><span class="sxs-lookup"><span data-stu-id="79705-153">**Internal/Ucwa**, **External/Ucwa** and **Ucwa** provide a means for clients to access the Unified Communications Web Application Programming Interface (UCWA API, or simply UCWA).</span></span> <span data-ttu-id="79705-154">`Internal/Ucwa`e `External/Ucwa` le directory virtuali sono punti di accesso riservati per il futuro miglioramento delle funzionalità e non vengono utilizzati.</span><span class="sxs-lookup"><span data-stu-id="79705-154">`Internal/Ucwa` and `External/Ucwa` virtual directories are access points reserved for future feature enhancement, and are not used.</span></span> <span data-ttu-id="79705-155">La `Ucwa` directory virtuale viene utilizzata per Microsoft Lync mobile (introdotta con Lync Server 2013) in tutti i dispositivi supportati.</span><span class="sxs-lookup"><span data-stu-id="79705-155">The `Ucwa` virtual directory is used for Microsoft Lync Mobile (introduced with Lync Server 2013) on all supported devices.</span></span> <span data-ttu-id="79705-156">Il servizio UCWA viene installato come parte del processo di distribuzione dei servizi Web interni di distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="79705-156">The UCWA service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

<span data-ttu-id="79705-157">`Internal/XFrame`, **External/Xframe** e **Xframe** forniscono l'accesso per le applicazioni server basate su UCWA.</span><span class="sxs-lookup"><span data-stu-id="79705-157">`Internal/XFrame`, **External/XFrame** and **XFrame** provide access for UCWA-based server applications.</span></span> <span data-ttu-id="79705-158">XFrame viene installato come parte del processo di distribuzione dei servizi Web di distribuzione di Lync Server 2013 interni.</span><span class="sxs-lookup"><span data-stu-id="79705-158">XFrame is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

<span data-ttu-id="79705-159">Il `Self` token si riferisce alle informazioni specifiche del client (tipo di risposta dell'utente) che effettua la richiesta.</span><span class="sxs-lookup"><span data-stu-id="79705-159">The `Self` token refers to information specific to the client (user response type) that is making the request.</span></span> <span data-ttu-id="79705-160">Il client che ha effettuato questa richiesta è stato esterno e questo riferimento per l'individuazione automatica si riferisce alla parte relativa all'utente del servizio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="79705-160">The client that made this request was external, and this Autodiscover reference is to the user portion of the Autodiscover service.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="79705-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79705-161">See Also</span></span>


[<span data-ttu-id="79705-162">Requisiti di sistema per i componenti per l'accesso degli utenti esterni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79705-162">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[<span data-ttu-id="79705-163">Pianificazione dell'individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79705-163">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

