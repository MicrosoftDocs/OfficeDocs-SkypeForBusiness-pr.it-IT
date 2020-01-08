---
title: "Lync Server 2013: informazioni sull'individuazione automatica"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding Autodiscover
ms:assetid: d70a15b7-750b-4e0f-9a7f-0254d6d486c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945654(v=OCS.15)
ms:contentKeyID: 51541522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae8a4965674952cfa5822c24e887ed4d5a02b798
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-autodiscover-in-lync-server-2013"></a><span data-ttu-id="75a0d-102">Informazioni sull'individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75a0d-102">Understanding Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75a0d-103">_**Argomento Ultima modifica:** 2013-06-03_</span><span class="sxs-lookup"><span data-stu-id="75a0d-103">_**Topic Last Modified:** 2013-06-03_</span></span>

<span data-ttu-id="75a0d-104">Il servizio di individuazione automatica di Lync Server 2013 è una funzionalità introdotta in origine in Microsoft Lync Server 2010 come parte dell'aggiornamento cumulativo per Lync Server 2010: novembre 2011.</span><span class="sxs-lookup"><span data-stu-id="75a0d-104">The Lync Server 2013 Autodiscover Service is a feature that was originally introduced in Microsoft Lync Server 2010 as part of the Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="75a0d-105">Oltre alle correzioni, questo aggiornamento cumulativo ha fornito il supporto per i client Lync mobile e Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="75a0d-105">In addition to fixes, this cumulative update delivered support for Lync Mobile and Lync 2013 clients.</span></span>

<span data-ttu-id="75a0d-106">In Lync Server 2013 il servizio di individuazione automatica fa parte integrante del funzionamento dei client mobili esterni e interni e viene esteso anche ai nuovi client, ad esempio l'app Lync di Windows Store recentemente introdotta per Windows 8.</span><span class="sxs-lookup"><span data-stu-id="75a0d-106">In Lync Server 2013, the Autodiscover Service is an integral part of the operation of external and internal mobile clients, and Autodiscover is also extended to new clients, such as the recently introduced Lync Windows Store app for Windows 8.</span></span> <span data-ttu-id="75a0d-107">L'individuazione automatica viene utilizzata anche dai client desktop di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="75a0d-107">Autodiscover is also used by the Lync 2013 desktop clients.</span></span> <span data-ttu-id="75a0d-108">L'individuazione automatica viene riconosciuta in Lync Server dai record DNS (Domain Name System) necessari \*\*lyncdiscover.\< Domain\> \*\* e **LyncdiscoverInternal.\< Domain\>**.</span><span class="sxs-lookup"><span data-stu-id="75a0d-108">Autodiscover is recognized in Lync Server by the required domain name system (DNS) records **lyncdiscover.\<domain\>** and **lyncdiscoverinternal.\<domain\>**.</span></span> <span data-ttu-id="75a0d-109">Inoltre, le versioni più recenti del client desktop Lync 2010 e Lync 2013 preferiscono l'individuazione automatica dei record SRV DNS (Domain Name System), usando i record SRV DNS solo se lyncdiscover. \<domain\> o LyncdiscoverInternal. \<il\> dominio non risponde o non si risolve.</span><span class="sxs-lookup"><span data-stu-id="75a0d-109">Additionally, newer versions of the Lync 2010 and Lync 2013 desktop client prefer Autodiscover over the domain name system (DNS) SRV records, using DNS SRV records only if lyncdiscover.\<domain\> or lyncdiscoverinternal.\<domain\> does not respond or does not resolve.</span></span> <span data-ttu-id="75a0d-110">L'app Lync di Windows Store per Windows 8 e Lync Mobile USA l'individuazione automatica esclusivamente e non si riferisce ai record SRV DNS tradizionali.</span><span class="sxs-lookup"><span data-stu-id="75a0d-110">The Lync Windows Store app for Windows 8 and Lync Mobile uses Autodiscover exclusively and will not refer to the traditional DNS SRV records.</span></span>

<span data-ttu-id="75a0d-111">In Lync Server 2013 l'individuazione automatica viene espansa per comunicare al client quali elementi, funzionalità e metodi di comunicazione sono disponibili per il client.</span><span class="sxs-lookup"><span data-stu-id="75a0d-111">In Lync Server 2013, Autodiscover is expanded to communicate to the client which elements, features, and communication methods are available to the client.</span></span> <span data-ttu-id="75a0d-112">Le informazioni vengono comunicate tramite una richiesta inviata dal client e i servizi Web di Lync Server rispondono con una risposta chiaramente definita che assegna un nome al client e come contattarle nel formato di individuazione automatica Documento di risposta.</span><span class="sxs-lookup"><span data-stu-id="75a0d-112">The information is communicated through a request that is sent from the client, and the Lync Server web services responds with a clearly defined response that names what is available to the client, and how to contact those features in the format of the Autodiscover Response document.</span></span>

<span data-ttu-id="75a0d-113">Il modo migliore per comprendere il documento di risposta di individuazione automatica, tra cui i servizi Web che comunicano le caratteristiche ai client tramite questo documento, consiste nel sezionare e definire ogni riga in una risposta tipica dal documento di risposta di individuazione automatica del servizio Web di Lync.</span><span class="sxs-lookup"><span data-stu-id="75a0d-113">The best way to understand the Autodiscover response document, including how the web services communicate features to clients through this document, is to dissect and define each line in a typical response from the Lync web service Autodiscover response document.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="75a0d-114">Nei dettagli che seguono l'utente ha già autenticato il server principale rispondendo a una richiesta di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="75a0d-114">In the details that follow, the user has already authenticated to the home server by responding to an authentication request.</span></span>



</div>

<div class="">


> [!NOTE]  
> <span data-ttu-id="75a0d-115">Il servizio Web di individuazione automatica di Lync è definito nei <STRONG>protocolli di Microsoft Office</STRONG> nella sezione <STRONG>specifiche aperte</STRONG> della raccolta MSDN ( <STRONG>Microsoft Developer Network</STRONG> ).</span><span class="sxs-lookup"><span data-stu-id="75a0d-115">The Lync Autodiscover Web Service is defined in the <STRONG>Microsoft Office Protocols</STRONG> in the <STRONG>Open Specifications</STRONG> section of the <STRONG>Microsoft Developer Network</STRONG> (MSDN) library.</span></span> <span data-ttu-id="75a0d-116">Per informazioni dettagliate, vedere il documento di specifica completo "protocollo di servizio Web individuazione automatica Lync" in <A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>:.</span><span class="sxs-lookup"><span data-stu-id="75a0d-116">For details, see the full specification document, "Lync Autodiscover Web Service Protocol," at: <A href="http://go.microsoft.com/fwlink/?linkid=273839">http://go.microsoft.com/fwlink/?LinkId=273839</A>.</span></span> <span data-ttu-id="75a0d-117">Per informazioni dettagliate sull'autenticazione, vedere "protocollo di servizio Web di autenticazione <A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>OC" all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="75a0d-117">For details about authentication, see "OC Authentication Web Service Protocol" at <A href="http://go.microsoft.com/fwlink/?linkid=279015">http://go.microsoft.com/fwlink/?LinkId=279015</A>.</span></span>



</div>

<div>

## <a name="the-lync-server-web-service-autodiscover-response"></a><span data-ttu-id="75a0d-118">Risposta di individuazione automatica del servizio Web di Lync Server</span><span class="sxs-lookup"><span data-stu-id="75a0d-118">The Lync Server Web Service Autodiscover Response</span></span>

<span data-ttu-id="75a0d-119">La risposta restituita quando viene inviata la richiesta di individuazione automatica è la stessa per un client interno o esterno.</span><span class="sxs-lookup"><span data-stu-id="75a0d-119">The response returned when the Autodiscover request is sent is the same for an internal or an external client.</span></span> <span data-ttu-id="75a0d-120">Alcuni parametri che hanno la posizione-Aware potrebbero cambiare.</span><span class="sxs-lookup"><span data-stu-id="75a0d-120">Some parameters that are location–aware may change.</span></span> <span data-ttu-id="75a0d-121">Se viene ricevuta una richiesta del client, ma il pool effettivo è diverso da quello che è stato contattato, il pool di Home dell'utente verrà impostato per l'utente.</span><span class="sxs-lookup"><span data-stu-id="75a0d-121">If a client request is received, but the actual pool is other than the one that has been contacted, the user’s home pool will be set for that user.</span></span> <span data-ttu-id="75a0d-122">Un collega il cui account utente si trova in un pool diverso, ma accedendo dalla stessa sede riceverebbe una risposta leggermente diversa.</span><span class="sxs-lookup"><span data-stu-id="75a0d-122">A colleague whose user account is on a different pool, but logging in from the same office, would get a slightly different response.</span></span> <span data-ttu-id="75a0d-123">La risposta indica il server front-end corretto o il pool Front-end per l'utente.</span><span class="sxs-lookup"><span data-stu-id="75a0d-123">The response indicates the correct Front End Server or Front End pool for that user.</span></span>

<span data-ttu-id="75a0d-124">Esempio di documento di risposta di individuazione automatica:</span><span class="sxs-lookup"><span data-stu-id="75a0d-124">An example of an Autodiscover Response document:</span></span>

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

## <a name="autodiscover-response-document-details"></a><span data-ttu-id="75a0d-125">Dettagli del documento di risposta di individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="75a0d-125">Autodiscover Response Document Details</span></span>

<span data-ttu-id="75a0d-126">Il documento di risposta di individuazione automatica può essere in uno dei due formati.</span><span class="sxs-lookup"><span data-stu-id="75a0d-126">The Autodiscover Response document can be in one of two formats.</span></span> <span data-ttu-id="75a0d-127">Il formato predefinito è JSON (JavaScript Object Notation).</span><span class="sxs-lookup"><span data-stu-id="75a0d-127">The default format is a JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="75a0d-128">L'altro formato è un documento XML (Extensible Markup Language).</span><span class="sxs-lookup"><span data-stu-id="75a0d-128">The other format is extensible markup language (XML) document.</span></span> <span data-ttu-id="75a0d-129">Per questo esempio viene usato il codice XML.</span><span class="sxs-lookup"><span data-stu-id="75a0d-129">The XML is used for this example.</span></span> <span data-ttu-id="75a0d-130">La richiesta e la risposta sono prevedibili perché il documento ha uno schema definito che determina il formato.</span><span class="sxs-lookup"><span data-stu-id="75a0d-130">The request and response are predictable because the document has a defined schema that determines the format.</span></span> <span data-ttu-id="75a0d-131">La riga del documento che descrive lo schema usato è la prima riga della richiesta o della risposta:</span><span class="sxs-lookup"><span data-stu-id="75a0d-131">The line in the document that describes the schema used is the first line in the request or response:</span></span>

    <AutodiscoverResponse xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" AccessLocation="External">

<span data-ttu-id="75a0d-132">La definizione di **AccessLocation = "External"** indica che la richiesta è stata effettuata da un utente esterno.</span><span class="sxs-lookup"><span data-stu-id="75a0d-132">The definition of **AccessLocation=”External”** indicates that the request was made from an external user.</span></span>

    <SipServerInternalAccess fqdn="pool01.contoso.com" port="5061"/>

&nbsp;

    <SipServerExternalAccess fqdn="sip.contoso.com" port="5061"/>

<span data-ttu-id="75a0d-133">SipServerInternalAccess e SipServerExternalAccess non sono attualmente usati.</span><span class="sxs-lookup"><span data-stu-id="75a0d-133">SipServerInternalAccess and SipServerExternalAccess are currently not used.</span></span> <span data-ttu-id="75a0d-134">Queste voci sono riservate per un uso futuro.</span><span class="sxs-lookup"><span data-stu-id="75a0d-134">These entries are reserved for future use.</span></span>

    <SipClientInternalAccess fqdn=" pool01.contoso.com" port="443"/>

&nbsp;

    <SipClientExternalAccess fqdn="sip.contoso.com " port="443"/>

<span data-ttu-id="75a0d-135">SipClientInternalAccess e SipClientExternalAccess descrivono il nome di dominio completo e la porta che un client interno o esterno userà per accedere al server SIP definito.</span><span class="sxs-lookup"><span data-stu-id="75a0d-135">SipClientInternalAccess and SipClientExternalAccess describe the fully qualified domain name and port that an internal or external client will use to access the defined SIP Server.</span></span> <span data-ttu-id="75a0d-136">Il client desktop Lync e l'app Lync di Windows Store usano queste voci, in base alla loro posizione (interna o esterna) per trovare il Director o il server front-end.</span><span class="sxs-lookup"><span data-stu-id="75a0d-136">The Lync desktop client and the Lync Windows Store app use these entries, based on their location (internal or external) to find the Director or Front End Server.</span></span>

    <Link token="Internal/Autodiscover" href="https://webinternal.contoso.net/Autodiscover/AutodiscoverService.svc/root"/>

&nbsp;

    <Link token ="External/Autodiscover" href="https://webexternal.contoso.com/Autodiscover/AutodiscoverService.svc/root"/>

<span data-ttu-id="75a0d-137">I `Autodiscover` riferimenti contengono i punti di ingresso del servizio per il servizio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="75a0d-137">The `Autodiscover` references contain the service entry points for the Autodiscover service.</span></span> <span data-ttu-id="75a0d-138">L'attributo token contiene il nome del servizio e l'href è un URL che definisce per il client in cui è possibile trovare il servizio.</span><span class="sxs-lookup"><span data-stu-id="75a0d-138">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="75a0d-139">I `External/Autodiscover`client in una rete esterna usano.</span><span class="sxs-lookup"><span data-stu-id="75a0d-139">Clients on an external network use the `External/Autodiscover`.</span></span> <span data-ttu-id="75a0d-140">Il servizio di individuazione automatica viene installato come parte del processo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="75a0d-140">The Autodiscover service is installed as part of the deployment process.</span></span> <span data-ttu-id="75a0d-141">`Internal/Autodiscover`non è attualmente usato ed è riservato per un uso futuro.</span><span class="sxs-lookup"><span data-stu-id="75a0d-141">`Internal/Autodiscover` is not currently used, and is reserved for future use.</span></span>

    <Link token="Internal/AuthBroker" href="https://webinternal.contoso.net/Reach/sip.svc"/>

&nbsp;

    <Link token="External/AuthBroker" href="https://webexternal.contoso.com/Reach/sip.svc"/>

<span data-ttu-id="75a0d-142">I `AuthBroker` riferimenti contengono i punti di ingresso del servizio per il servizio di broker di autenticazione interni e esterni, in questo caso SIP. svc.</span><span class="sxs-lookup"><span data-stu-id="75a0d-142">The `AuthBroker` references contain the service entry points for the internal and the external authentication broker service, in this case, sip.svc.</span></span> <span data-ttu-id="75a0d-143">L'attributo token contiene il nome del servizio e l'href è un URL che definisce per il client in cui è possibile trovare il servizio.</span><span class="sxs-lookup"><span data-stu-id="75a0d-143">The token attribute contains the name of the service, and the href is a URL that defines for the client where the service can be found.</span></span> <span data-ttu-id="75a0d-144">Client della rete interna con l'utilizzo `Internal/AuthBroker`.</span><span class="sxs-lookup"><span data-stu-id="75a0d-144">Clients on the internal network with use `Internal/AuthBroker`.</span></span> <span data-ttu-id="75a0d-145">I `External/AuthBroker`client in una rete esterna usano.</span><span class="sxs-lookup"><span data-stu-id="75a0d-145">Clients on an external network use the `External/AuthBroker`.</span></span> <span data-ttu-id="75a0d-146">Il servizio AuthBroker viene installato come parte del processo di distribuzione dei servizi Web di distribuzione di Lync Server 2013 interni.</span><span class="sxs-lookup"><span data-stu-id="75a0d-146">The AuthBroker service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/WebScheduler" href="https://webinternal.contoso.net/Scheduler"/>

&nbsp;

    <Link token="External/WebScheduler" href="https://webexternal.contoso.com/Scheduler"/>

<span data-ttu-id="75a0d-147">Il `WebScheduler` token fa riferimento agli URL per l'accesso client alla programmazione basata sul Web per le conferenze di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="75a0d-147">The `WebScheduler` token references the URLs for client access to the web-based scheduling for Lync Server conferences.</span></span> <span data-ttu-id="75a0d-148">Attualmente viene usato solo `External/WebScheduler` il.</span><span class="sxs-lookup"><span data-stu-id="75a0d-148">Currently, only the `External/WebScheduler` is used.</span></span> <span data-ttu-id="75a0d-149">Webscheduler viene installato come parte del processo di distribuzione dei servizi Web di distribuzione di Lync Server 2013 interni.</span><span class="sxs-lookup"><span data-stu-id="75a0d-149">The WebScheduler is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Mcx" href="https://webexternal.contoso.net/Mcx/McxService.svc"/>

&nbsp;

    <Link token="External/Mcx" href="https://webexternal.contoso.com/Mcx/McxService.svc"/>

<span data-ttu-id="75a0d-150">`Internal/Mcx`e `External/Mcx` sono le posizioni dei servizi per dispositivi mobili, introdotte in aggiornamento cumulativo per Lync Server 2010: novembre 2011.</span><span class="sxs-lookup"><span data-stu-id="75a0d-150">`Internal/Mcx` and `External/Mcx` are the locations of the Mobility services, introduced in Cumulative Update for Lync Server 2010: November 2011.</span></span> <span data-ttu-id="75a0d-151">Questi riferimenti continueranno a essere usati da Lync 2010 mobile in tutti i dispositivi supportati.</span><span class="sxs-lookup"><span data-stu-id="75a0d-151">These references will continue to be used by Lync 2010 Mobile on all supported devices.</span></span> <span data-ttu-id="75a0d-152">Il servizio MCX viene installato come parte del processo di distribuzione dei servizi Web di distribuzione di Lync Server 2013 interni.</span><span class="sxs-lookup"><span data-stu-id="75a0d-152">The Mcx service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/Ucwa" href="https://webinternal.contoso.net/ucwa/v1/applications"/>

&nbsp;

    <Link token="External/Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

&nbsp;

    <Link token="Ucwa" href="https://webexternal.contoso.com/ucwa/v1/applications"/>

<span data-ttu-id="75a0d-153">**Internal/UCWA**, **External/UCWA** e **UCWA** offre ai client l'accesso all'interfaccia di programmazione delle applicazioni Web Unified Communications (UCWA API o semplicemente UCWA).</span><span class="sxs-lookup"><span data-stu-id="75a0d-153">**Internal/Ucwa**, **External/Ucwa** and **Ucwa** provide a means for clients to access the Unified Communications Web Application Programming Interface (UCWA API, or simply UCWA).</span></span> <span data-ttu-id="75a0d-154">`Internal/Ucwa`e `External/Ucwa` le directory virtuali sono punti di accesso riservati per il miglioramento delle caratteristiche future e non vengono usati.</span><span class="sxs-lookup"><span data-stu-id="75a0d-154">`Internal/Ucwa` and `External/Ucwa` virtual directories are access points reserved for future feature enhancement, and are not used.</span></span> <span data-ttu-id="75a0d-155">La `Ucwa` directory virtuale viene usata per Microsoft Lync mobile (introdotta con Lync Server 2013) in tutti i dispositivi supportati.</span><span class="sxs-lookup"><span data-stu-id="75a0d-155">The `Ucwa` virtual directory is used for Microsoft Lync Mobile (introduced with Lync Server 2013) on all supported devices.</span></span> <span data-ttu-id="75a0d-156">Il servizio UCWA viene installato come parte del processo di distribuzione dei servizi Web di distribuzione di Lync Server 2013 interni.</span><span class="sxs-lookup"><span data-stu-id="75a0d-156">The UCWA service is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Internal/XFrame" href="https://webinternal.contoso.net/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="External/XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

&nbsp;

    <Link token="XFrame" href="https://webexternal.contoso.com/Autodiscover/XFrame/XFrame.html"/>

<span data-ttu-id="75a0d-157">`Internal/XFrame`, **External/Xframe** e **Xframe** consentono l'accesso per le applicazioni server basate su UCWA.</span><span class="sxs-lookup"><span data-stu-id="75a0d-157">`Internal/XFrame`, **External/XFrame** and **XFrame** provide access for UCWA-based server applications.</span></span> <span data-ttu-id="75a0d-158">XFrame viene installato come parte del processo di distribuzione dei servizi Web di distribuzione di Lync Server 2013 interni.</span><span class="sxs-lookup"><span data-stu-id="75a0d-158">XFrame is installed as part of the deployment process of your internal Lync Server 2013 deployment web services.</span></span>

    <Link token="Self" href="https://webexternal.contoso.net/Autodiscover/AutodiscoverService.svc/root/user"/>

<span data-ttu-id="75a0d-159">Il `Self` token fa riferimento a informazioni specifiche del client (tipo di risposta utente) che sta effettuando la richiesta.</span><span class="sxs-lookup"><span data-stu-id="75a0d-159">The `Self` token refers to information specific to the client (user response type) that is making the request.</span></span> <span data-ttu-id="75a0d-160">Il client che ha eseguito questa richiesta è stato esterno e questo riferimento per l'individuazione automatica si riferisce alla parte dell'utente del servizio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="75a0d-160">The client that made this request was external, and this Autodiscover reference is to the user portion of the Autodiscover service.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="75a0d-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75a0d-161">See Also</span></span>


[<span data-ttu-id="75a0d-162">Requisiti di sistema per i componenti per l'accesso degli utenti esterni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75a0d-162">System requirements for external user access components for Lync Server 2013</span></span>](lync-server-2013-system-requirements-for-external-user-access-components.md)  
[<span data-ttu-id="75a0d-163">Pianificazione per l'individuazione automatica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75a0d-163">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

