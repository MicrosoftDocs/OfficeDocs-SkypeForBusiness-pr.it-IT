---
title: 'Lync Server 2013: requisiti del servizio di individuazione automatica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5cf4a26c9f0b36cd239daabbc2538716e2bcd3c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515773"
---
# <a name="autodiscover-service-requirements-for-lync-server-2013"></a><span data-ttu-id="ec43f-102">Requisiti del servizio di individuazione automatica per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec43f-102">Autodiscover service requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec43f-103">_**Ultimo argomento modificato:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="ec43f-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="ec43f-104">Il servizio di individuazione automatica di Microsoft Lync Server 2013 viene eseguito nei server Director e front end pool e, se pubblicato in DNS, può essere utilizzato dai dispositivi mobili che eseguono Lync mobile per individuare i servizi di mobilità.</span><span class="sxs-lookup"><span data-stu-id="ec43f-104">The Microsoft Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by mobile devices running Lync Mobile to locate mobility services.</span></span> <span data-ttu-id="ec43f-105">Prima che i dispositivi mobili che eseguono Lync mobile possano trarre vantaggio dall'individuazione automatica, è necessario modificare gli elenchi di nomi alternativi del soggetto del certificato su qualsiasi server Director e front end che esegue il servizio di Autodiscover.</span><span class="sxs-lookup"><span data-stu-id="ec43f-105">Before mobile devices running Lync Mobile can take advantage of automatic discovery, you need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="ec43f-106">Potrebbe inoltre essere necessario modificare gli elenchi dei nomi alternativi del soggetto nei certificati utilizzati per le regole di pubblicazione dei servizi Web esterni nei proxy inversi.</span><span class="sxs-lookup"><span data-stu-id="ec43f-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="ec43f-107">Per informazioni dettagliate sulle voci dei nomi alternativi del soggetto necessarie per i direttori, i Front End Server e i proxy inversi, vedere [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.</span><span class="sxs-lookup"><span data-stu-id="ec43f-107">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.</span></span>

<span data-ttu-id="ec43f-108">La decisione relativa agli elenchi dei nomi alternativi del soggetto nei proxy inversi dipende dal fatto che il servizio di individuazione automatica venga pubblicato sulla porta 80 o sulla porta 443:</span><span class="sxs-lookup"><span data-stu-id="ec43f-108">The decision about using subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="ec43f-109">**Pubblicati sulla porta 80**     Non sono necessarie modifiche ai certificati se la query iniziale al servizio di individuazione automatica si verifica sulla porta 80.</span><span class="sxs-lookup"><span data-stu-id="ec43f-109">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="ec43f-110">Ciò è dovuto al fatto che i dispositivi mobili che eseguono Lync accederanno al proxy inverso sulla porta 80 esternamente e quindi verranno reindirizzati a un server Director o front end su porta 8080 internamente.</span><span class="sxs-lookup"><span data-stu-id="ec43f-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="ec43f-111">Per informazioni dettagliate, vedere la sezione "Processo di individuazione automatica iniziale tramite la porta 80" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ec43f-111">For details, see the “Initial Autodiscover Process Using Port 80” section later in this topic.</span></span>

  - <span data-ttu-id="ec43f-112">**Pubblicati sulla porta 443**     L'elenco dei nomi alternativi del soggetto nei certificati utilizzati dalla regola di pubblicazione dei servizi Web esterni deve contenere un \*lyncdiscover. \<sipdomain\> \*</span><span class="sxs-lookup"><span data-stu-id="ec43f-112">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>*</span></span> <span data-ttu-id="ec43f-113">voce per ogni dominio SIP all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ec43f-113">entry for each SIP domain within your organization.</span></span>

<span data-ttu-id="ec43f-114">La riemissione dei certificati tramite un'autorità di certificazione interna in genere è un processo semplice, ma per i certificati pubblici utilizzati nella regola di pubblicazione dei servizi Web l'aggiunta di più voci dei nomi alternativi del soggetto può diventare un'attività dispendiosa.</span><span class="sxs-lookup"><span data-stu-id="ec43f-114">Reissuing certificates using an internal certificate authority is typically a simple process but for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="ec43f-115">Per ovviare a questo problema, è supportata la connessione di individuazione automatica iniziale tramite la porta 80, che viene quindi reindirizzata alla porta 8080 nel server Director o front end.</span><span class="sxs-lookup"><span data-stu-id="ec43f-115">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<span data-ttu-id="ec43f-116">Si supponga, ad esempio, che un client mobile che esegue Lync mobile sia configurato per l'accesso a Lync Server 2013 utilizzando la funzionalità di individuazione automatica tramite HTTP per la richiesta iniziale.</span><span class="sxs-lookup"><span data-stu-id="ec43f-116">For example, assume that a mobile client running Lync Mobile is configured to sign in to Lync Server 2013 using the automatic discovery feature using HTTP for the initial request.</span></span>

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a><span data-ttu-id="ec43f-117">Processo di individuazione automatica iniziale per i dispositivi mobili tramite la porta 80</span><span class="sxs-lookup"><span data-stu-id="ec43f-117">Initial Autodiscover Process for Mobile Devices Using Port 80</span></span>

1.  <span data-ttu-id="ec43f-118">Il dispositivo mobile che esegue Lync mobile cerca lyncdiscover.contoso.com con DNS, dove esiste un record A.</span><span class="sxs-lookup"><span data-stu-id="ec43f-118">Mobile device running Lync Mobile looks up lyncdiscover.contoso.com using DNS, where an A record exists.</span></span>

2.  <span data-ttu-id="ec43f-119">DNS esterno restituisce l'indirizzo IP per i servizi Web esterni al client.</span><span class="sxs-lookup"><span data-stu-id="ec43f-119">External DNS returns the IP address for the external web services to the client.</span></span>

3.  <span data-ttu-id="ec43f-120">Dispositivo mobile che esegue Lync mobile invia http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com una richiesta al proxy inverso</span><span class="sxs-lookup"><span data-stu-id="ec43f-120">Mobile device running Lync Mobile sends request http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com to the reverse proxy</span></span>

4.  <span data-ttu-id="ec43f-121">La regola di pubblicazione Web colmerà la richiesta dalla porta 80 esternamente alla porta 8080 internamente, che lo instraderà a un Director o a un front end server.</span><span class="sxs-lookup"><span data-stu-id="ec43f-121">The web publishing rule will bridge the request from port 80 externally to port 8080 internally, which will then route it to either a Director or Front End Server.</span></span>
    
    <span data-ttu-id="ec43f-122">Poiché si tratta di una richiesta HTTP e non HTTPS, per supportare il servizio di individuazione automatica non sono necessarie modifiche per il certificato nella regola di pubblicazione dei servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="ec43f-122">Since the request is HTTP and not HTTPS, no modifications are needed to the certificate on the external web service publishing rule to support the Autodiscover Service.</span></span>

5.  <span data-ttu-id="ec43f-123">Il servizio di individuazione automatica restituisce gli URL dei servizi Web esterni nel formato HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ec43f-123">The Autodiscover Service returns the external web service URLs (in HTTPS format).</span></span>

6.  <span data-ttu-id="ec43f-124">Il dispositivo mobile che esegue Lync mobile può quindi riconnettersi al proxy inverso sulla porta 443 ed essere reindirizzato su 4443 al servizio per dispositivi mobili in esecuzione nel pool di casa dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ec43f-124">The mobile device running Lync Mobile can then reconnect to the reverse proxy on port 443 and is redirected over 4443 to the mobility service running on the user’s home pool.</span></span>
    
    <span data-ttu-id="ec43f-125">Poiché la query HTTPS riguarda l'URL dei servizi Web esterni e non l'URL del servizio di individuazione automatica, ha esito positivo perché il certificato conterrà già le voci dei nomi alternativi del soggetto per i nomi di dominio completi (FQDN) dei servizi Web esterni.</span><span class="sxs-lookup"><span data-stu-id="ec43f-125">Since the HTTPS query is to the external web services URL vs. the Autodiscover Service URL, it succeeds because the certificate will already contain subject alternative name entries for the external web services fully qualified domain names (FQDNs).</span></span>
    
    <span data-ttu-id="ec43f-126">In questo scenario non è necessario apportare modifiche ai certificati per supportare i servizi per dispositivi mobili.</span><span class="sxs-lookup"><span data-stu-id="ec43f-126">In this scenario, there are no certificate changes required to support mobility.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ec43f-127">Se nel server Web di destinazione è presente un certificato che include lyncdiscover.contoso.com come valore dell'elenco dei nomi alternativi del soggetto:</span><span class="sxs-lookup"><span data-stu-id="ec43f-127">If the target web server has a certificate that does not have a matching value for lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="ec43f-128">a. &nbsp; &nbsp; &nbsp; Il server Web risponde con un "Server Hello" e nessun certificato.</span><span class="sxs-lookup"><span data-stu-id="ec43f-128">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server Hello” and no certificate.</span></span><BR><span data-ttu-id="ec43f-129">b. &nbsp; &nbsp; &nbsp; Il dispositivo mobile che esegue Lync mobile interrompe immediatamente la sessione.</span><span class="sxs-lookup"><span data-stu-id="ec43f-129">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile immediately terminates the session.</span></span><BR><span data-ttu-id="ec43f-130">Se nel server Web di destinazione è presente un certificato che include lyncdiscover.contoso.com come valore dell'elenco dei nomi alternativi del soggetto:</span><span class="sxs-lookup"><span data-stu-id="ec43f-130">If the target web server has a certificate that includes lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="ec43f-131">a. &nbsp; &nbsp; &nbsp; Il server Web risponde con un "Server Hello" e un certificato.</span><span class="sxs-lookup"><span data-stu-id="ec43f-131">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server hello” and a certificate.</span></span><BR><span data-ttu-id="ec43f-132">b. &nbsp; &nbsp; &nbsp; Il dispositivo mobile che esegue Lync mobile convalida il certificato e completa l'handshake.</span><span class="sxs-lookup"><span data-stu-id="ec43f-132">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile validates the certificate and completes the handshake.</span></span>

    
    </div>

<span data-ttu-id="ec43f-133">Per supportare una connessione iniziale al servizio di individuazione automatica utilizzando la porta 80 nel server proxy inverso, è possibile creare una regola di pubblicazione http simile a questo esempio per una regola di pubblicazione Web di proxy inverso di Forefront Threat Management Gateway 2010:</span><span class="sxs-lookup"><span data-stu-id="ec43f-133">To support an initial connection to the Autodiscover Service using port 80 on your reverse proxy server, you can create an http publishing rule similar to this example for a Forefront Threat Management Gateway 2010 reverse proxy web publishing rule:</span></span>

1.  <span data-ttu-id="ec43f-134">Creare una nuova regola di pubblicazione Web, ad esempio **Individuazione automatica Lync Server (HTTP)**.</span><span class="sxs-lookup"><span data-stu-id="ec43f-134">Create a new web publishing rule (for example, **Lync Server Autodiscover (HTTP)**).</span></span>

2.  <span data-ttu-id="ec43f-135">In **Nome pubblico** immettere lyncdiscover.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ec43f-135">In **Public Name**, enter lyncdiscover.contoso.com.</span></span>

3.  <span data-ttu-id="ec43f-136">Nella scheda **Bridging** selezionare solo l'opzione per inoltrare le richieste dalla porta 80 alla porta 8080.</span><span class="sxs-lookup"><span data-stu-id="ec43f-136">On the **Bridging** tab, select only the option to bridge requests from Port 80 to Port 8080.</span></span>

4.  <span data-ttu-id="ec43f-137">Nella scheda **Autenticazione** selezionare **Nessuna delega.\*\*\*\*Il client non può eseguire l'autenticazione direttamente**.</span><span class="sxs-lookup"><span data-stu-id="ec43f-137">On the **Authentication** tab, select **No authentication**, and **Client cannot authenticate directly**.</span></span>

5.  <span data-ttu-id="ec43f-138">Eseguire il commit delle modifiche e spostare la regola all'inizio dell'elenco delle regole di Lync (primo in ordine di elaborazione).</span><span class="sxs-lookup"><span data-stu-id="ec43f-138">Commit changes, and move the rule to the top of the list of Lync rules (first in processing order).</span></span>

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="ec43f-139">Mobilità per la distribuzione del dominio diviso</span><span class="sxs-lookup"><span data-stu-id="ec43f-139">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="ec43f-140">Uno spazio indirizzo SIP condiviso, noto anche come *dominio diviso* o *distribuzione ibrida*, è una configurazione in cui gli utenti sono distribuiti in una distribuzione locale e un ambiente online.</span><span class="sxs-lookup"><span data-stu-id="ec43f-140">A shared SIP address space, also known as a *split-domain*, or a *hybrid deployment* is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="ec43f-141">Il risultato desiderato è che gli utenti, indipendentemente dalla posizione in cui si trova il server principale (in locale oppure online), accedano alla distribuzione e vengano reindirizzati alla posizione del server principale.</span><span class="sxs-lookup"><span data-stu-id="ec43f-141">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), to log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="ec43f-142">A tale scopo, la caratteristica di individuazione automatica di Microsoft Lync Server 2013 viene utilizzata per reindirizzare l'utente online alla topologia online.</span><span class="sxs-lookup"><span data-stu-id="ec43f-142">To accomplish this, the Autodiscover feature of Microsoft Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="ec43f-143">Per ottenere questo risultato, è necessario configurare l'URL (Uniform Resource Locator) di individuazione automatica utilizzando Lync Server Management Shell e i cmdlet **Get-CsHostingProvider** e **Set-CsHostingProvider**.</span><span class="sxs-lookup"><span data-stu-id="ec43f-143">This is done by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell and the cmdlets **Get-CsHostingProvider** and **Set-CsHostingProvider**.</span></span>

<span data-ttu-id="ec43f-144">Sarà necessario raccogliere e prendere nota degli attributi distribuiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec43f-144">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="ec43f-145">Da Lync Server Management Shell, digitare</span><span class="sxs-lookup"><span data-stu-id="ec43f-145">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="ec43f-p106">Nei risultati, individuare il provider online con l'attributo **ProxyFQDN**. Ad esempio, sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="ec43f-p106">In the results, find the online provider with the attribute **ProxyFQDN**. For example, sipfed.online.lync.com</span></span>

  - <span data-ttu-id="ec43f-148">Prendere nota del valore di ProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="ec43f-148">Record the value of the ProxyFQDN</span></span>

  - <span data-ttu-id="ec43f-149">Abilitare la Federazione nel pannello di controllo di Lync Server locale, consentendo la Federazione con il provider online</span><span class="sxs-lookup"><span data-stu-id="ec43f-149">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider</span></span>

  - <span data-ttu-id="ec43f-p107">Abilitare la federazione per il provider online. Per impostazione predefinita, tutti gli utenti online sono abilitati per la federazione dei domini e possono comunicare con tutti i domini</span><span class="sxs-lookup"><span data-stu-id="ec43f-p107">Enable federation for the online provider. By default, all online users are enabled for domain federation and can communicate with all domains</span></span>

  - <span data-ttu-id="ec43f-152">Se si prevede di definire domini bloccati e consentiti, determinare i domini che verranno esplicitamente consentiti o bloccati</span><span class="sxs-lookup"><span data-stu-id="ec43f-152">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block</span></span>

  - <span data-ttu-id="ec43f-153">Per la federazione online è necessario pianificare le eccezioni del firewall, i certificati e i record dell'host DNS (A oppure AAAA se si utilizza IPv6).</span><span class="sxs-lookup"><span data-stu-id="ec43f-153">For online federation, you must plan for firewall exceptions, certificates and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="ec43f-154">È inoltre necessario configurare i criteri di federazione.</span><span class="sxs-lookup"><span data-stu-id="ec43f-154">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="ec43f-155">Per informazioni dettagliate, vedere [Planning for Lync Server 2013 and Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="ec43f-155">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

