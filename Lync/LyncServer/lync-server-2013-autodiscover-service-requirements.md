---
title: 'Lync Server 2013: Requisiti del servizio di individuazione automatica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Autodiscover service requirements
ms:assetid: 0ac5dbf7-9acd-4d25-b21a-932022b8b983
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690012(v=OCS.15)
ms:contentKeyID: 48183368
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea9d9be05561d200696a5ad0256c0d5424cf9b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="autodiscover-service-requirements-for-lync-server-2013"></a><span data-ttu-id="0fe6b-102">Requisiti del servizio di individuazione automatica per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0fe6b-102">Autodiscover service requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0fe6b-103">_**Argomento Ultima modifica:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="0fe6b-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="0fe6b-104">Il servizio di individuazione automatica di Microsoft Lync Server 2013 viene eseguito nei server Director e front end pool e, se pubblicato in DNS, può essere usato dai dispositivi mobili che usano Lync mobile per individuare i servizi di mobilità.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-104">The Microsoft Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by mobile devices running Lync Mobile to locate mobility services.</span></span> <span data-ttu-id="0fe6b-105">Prima che i dispositivi mobili che utilizzano Lync mobile possano sfruttare l'individuazione automatica, è necessario modificare gli elenchi di nomi alternativi del soggetto del certificato in qualsiasi Director e front end server che gestisce il servizio di rilevamento automatico.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-105">Before mobile devices running Lync Mobile can take advantage of automatic discovery, you need to modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="0fe6b-106">Può essere inoltre necessario modificare gli elenchi di nomi alternativi oggetto nei certificati usati per le regole di pubblicazione dei servizi Web esterni nei proxy inversi.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="0fe6b-107">Per informazioni dettagliate sulle voci di nome alternative oggetto necessarie per direttori, server front-end e reverse proxy, vedere [requisiti tecnici per la mobilità in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) nella pianificazione della mobilità.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-107">For details about the subject alternative name entries that are required for Directors, Front End Servers, and reverse proxies, see [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md) in Planning for Mobility.</span></span>

<span data-ttu-id="0fe6b-108">La decisione relativa all'uso di elenchi di nomi alternativi per i proxy inversi si basa sulla possibilità di pubblicare il servizio di individuazione automatica sulla porta 80 o sulla porta 443:</span><span class="sxs-lookup"><span data-stu-id="0fe6b-108">The decision about using subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="0fe6b-109">**Pubblicato sulla porta 80**   non sono necessarie modifiche al certificato se la query iniziale per il servizio di individuazione automatica si verifica sulla porta 80.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-109">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="0fe6b-110">Il motivo è che i dispositivi mobili che utilizzano Lync accederanno al proxy inverso sulla porta 80 esternamente e quindi verranno reindirizzati a un amministratore o a un server front-end sulla porta 8080 internamente.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be redirected to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="0fe6b-111">Per informazioni dettagliate, vedere la sezione "processo di individuazione automatica iniziale tramite la porta 80" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-111">For details, see the “Initial Autodiscover Process Using Port 80” section later in this topic.</span></span>

  - <span data-ttu-id="0fe6b-112">**Pubblicato in porta 443**   l'elenco dei nomi alternativi oggetto nei certificati usati dalla regola di pubblicazione dei servizi Web esterni deve contenere un \*lyncdiscover.\< SipDomain\> \* voce per ogni dominio SIP all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-112">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>

<span data-ttu-id="0fe6b-113">La riemissione di certificati tramite un'autorità di certificazione interna è in genere un processo semplice, ma per i certificati pubblici usati nella regola di pubblicazione del servizio Web, l'aggiunta di più voci di nomi alternativi soggetto può diventare costosa.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-113">Reissuing certificates using an internal certificate authority is typically a simple process but for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="0fe6b-114">Per risolvere il problema, è supportata la connessione di individuazione automatica iniziale tramite la porta 80, che viene quindi reindirizzata alla porta 8080 nel server Director o front end.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-114">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<span data-ttu-id="0fe6b-115">Supponiamo ad esempio che un client mobile che usa Lync mobile sia configurato per accedere a Lync Server 2013 usando la funzionalità di individuazione automatica tramite HTTP per la richiesta iniziale.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-115">For example, assume that a mobile client running Lync Mobile is configured to sign in to Lync Server 2013 using the automatic discovery feature using HTTP for the initial request.</span></span>

<div>

## <a name="initial-autodiscover-process-for-mobile-devices-using-port-80"></a><span data-ttu-id="0fe6b-116">Processo di individuazione automatica iniziale per i dispositivi mobili tramite la porta 80</span><span class="sxs-lookup"><span data-stu-id="0fe6b-116">Initial Autodiscover Process for Mobile Devices Using Port 80</span></span>

1.  <span data-ttu-id="0fe6b-117">Il dispositivo mobile che usa Lync mobile cerca lyncdiscover.contoso.com con DNS, dove esiste un record A.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-117">Mobile device running Lync Mobile looks up lyncdiscover.contoso.com using DNS, where an A record exists.</span></span>

2.  <span data-ttu-id="0fe6b-118">DNS esterno restituisce l'indirizzo IP per i servizi Web esterni al client.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-118">External DNS returns the IP address for the external web services to the client.</span></span>

3.  <span data-ttu-id="0fe6b-119">Dispositivo mobile che esegue Lync mobile invia http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com una richiesta al proxy inverso</span><span class="sxs-lookup"><span data-stu-id="0fe6b-119">Mobile device running Lync Mobile sends request http://lyncdiscover.contoso.com?sipuri=lyncUser1@contoso.com to the reverse proxy</span></span>

4.  <span data-ttu-id="0fe6b-120">La regola di pubblicazione Web eseguirà il Bridge della richiesta dalla porta 80 esternamente alla porta 8080 internamente, che lo instraderà a un amministratore o a un server front-end.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-120">The web publishing rule will bridge the request from port 80 externally to port 8080 internally, which will then route it to either a Director or Front End Server.</span></span>
    
    <span data-ttu-id="0fe6b-121">Dato che la richiesta è HTTP e non HTTPS, non è necessario apportare modifiche al certificato della regola di pubblicazione del servizio Web esterno per supportare il servizio di individuazione automatica.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-121">Since the request is HTTP and not HTTPS, no modifications are needed to the certificate on the external web service publishing rule to support the Autodiscover Service.</span></span>

5.  <span data-ttu-id="0fe6b-122">Il servizio di individuazione automatica restituisce gli URL del servizio Web esterno (in formato HTTPS).</span><span class="sxs-lookup"><span data-stu-id="0fe6b-122">The Autodiscover Service returns the external web service URLs (in HTTPS format).</span></span>

6.  <span data-ttu-id="0fe6b-123">Il dispositivo mobile che utilizza Lync mobile può quindi riconnettersi al proxy inverso sulla porta 443 e viene reindirizzato su 4443 al servizio di mobilità in uso nel pool Home dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-123">The mobile device running Lync Mobile can then reconnect to the reverse proxy on port 443 and is redirected over 4443 to the mobility service running on the user’s home pool.</span></span>
    
    <span data-ttu-id="0fe6b-124">Poiché la query HTTPS è per l'URL dei servizi Web esterni e l'URL del servizio di individuazione automatica, viene eseguita correttamente perché il certificato includerà già voci di nome alternative per i servizi Web esterni, nomi di dominio completi.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-124">Since the HTTPS query is to the external web services URL vs. the Autodiscover Service URL, it succeeds because the certificate will already contain subject alternative name entries for the external web services fully qualified domain names (FQDNs).</span></span>
    
    <span data-ttu-id="0fe6b-125">In questo scenario non sono necessarie modifiche al certificato per supportare la mobilità.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-125">In this scenario, there are no certificate changes required to support mobility.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0fe6b-126">Se il server Web di destinazione ha un certificato che non ha un valore corrispondente per lyncdiscover.contoso.com come valore di elenco nome alternativo soggetto:</span><span class="sxs-lookup"><span data-stu-id="0fe6b-126">If the target web server has a certificate that does not have a matching value for lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="0fe6b-127">a.&nbsp;&nbsp;&nbsp;Web server risponde con un "Server Hello" e nessun certificato.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-127">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server Hello” and no certificate.</span></span><BR><span data-ttu-id="0fe6b-128">b.&nbsp;&nbsp;&nbsp;un dispositivo mobile con Lync mobile termina immediatamente la sessione.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-128">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile immediately terminates the session.</span></span><BR><span data-ttu-id="0fe6b-129">Se il server Web di destinazione ha un certificato che include lyncdiscover.contoso.com come valore di elenco nome alternativo soggetto:</span><span class="sxs-lookup"><span data-stu-id="0fe6b-129">If the target web server has a certificate that includes lyncdiscover.contoso.com as a subject alternative name list value:</span></span><BR><span data-ttu-id="0fe6b-130">a.&nbsp;&nbsp;&nbsp;Web server risponde con un "Server Hello" e un certificato.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-130">a.&nbsp;&nbsp;&nbsp;Web server responds with a “Server hello” and a certificate.</span></span><BR><span data-ttu-id="0fe6b-131">b.&nbsp;&nbsp;&nbsp;dispositivo mobile che utilizza Lync mobile convalida il certificato e completa l'handshake.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-131">b.&nbsp;&nbsp;&nbsp;Mobile device running Lync Mobile validates the certificate and completes the handshake.</span></span>

    
    </div>

<span data-ttu-id="0fe6b-132">Per supportare una connessione iniziale al servizio di individuazione automatica tramite la porta 80 nel server proxy inverso, è possibile creare una regola di pubblicazione http simile a questo esempio per una regola di pubblicazione Web proxy inversa del gateway di Forefront Threat Management 2010:</span><span class="sxs-lookup"><span data-stu-id="0fe6b-132">To support an initial connection to the Autodiscover Service using port 80 on your reverse proxy server, you can create an http publishing rule similar to this example for a Forefront Threat Management Gateway 2010 reverse proxy web publishing rule:</span></span>

1.  <span data-ttu-id="0fe6b-133">Creare una nuova regola di pubblicazione Web, ad esempio **Lync Server autodiscover (http)**).</span><span class="sxs-lookup"><span data-stu-id="0fe6b-133">Create a new web publishing rule (for example, **Lync Server Autodiscover (HTTP)**).</span></span>

2.  <span data-ttu-id="0fe6b-134">In **nome pubblico**immettere lyncdiscover.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-134">In **Public Name**, enter lyncdiscover.contoso.com.</span></span>

3.  <span data-ttu-id="0fe6b-135">Nella scheda **bridging** selezionare solo l'opzione per eseguire il Bridge delle richieste dalla porta 80 alla porta 8080.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-135">On the **Bridging** tab, select only the option to bridge requests from Port 80 to Port 8080.</span></span>

4.  <span data-ttu-id="0fe6b-136">Nella scheda **autenticazione** selezionare **Nessuna autenticazione**e il **client non può eseguire**l'autenticazione direttamente.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-136">On the **Authentication** tab, select **No authentication**, and **Client cannot authenticate directly**.</span></span>

5.  <span data-ttu-id="0fe6b-137">Confermare le modifiche e posizionare la regola all'inizio dell'elenco delle regole di Lync (prima in ordine di elaborazione).</span><span class="sxs-lookup"><span data-stu-id="0fe6b-137">Commit changes, and move the rule to the top of the list of Lync rules (first in processing order).</span></span>

</div>

<div>

## <a name="mobility-for-the-split-domain-deployment"></a><span data-ttu-id="0fe6b-138">Mobilità per la distribuzione di domini divisi</span><span class="sxs-lookup"><span data-stu-id="0fe6b-138">Mobility for the Split Domain Deployment</span></span>

<span data-ttu-id="0fe6b-139">Uno spazio di indirizzi SIP condiviso, noto anche come *Split-Domain*o una *distribuzione ibrida* , è una configurazione in cui gli utenti vengono distribuiti in una distribuzione locale e in un ambiente online.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-139">A shared SIP address space, also known as a *split-domain*, or a *hybrid deployment* is a configuration where users are deployed across an on-premise deployment and an online environment.</span></span> <span data-ttu-id="0fe6b-140">Il risultato desiderato consiste nell'avere un utente, indipendentemente da dove si trova il proprio Home Server (locale o online), per accedere alla distribuzione ed essere reindirizzati alla posizione del proprio Home Server.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-140">The desired outcome is to have a user, regardless of where their home server is located (on-premise or online), to log into the deployment and be redirected to their home server location.</span></span> <span data-ttu-id="0fe6b-141">A questo scopo, la funzionalità di individuazione automatica di Microsoft Lync Server 2013 viene usata per reindirizzare l'utente online alla topologia online.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-141">To accomplish this, the Autodiscover feature of Microsoft Lync Server 2013 is used to redirect the online user to the online topology.</span></span> <span data-ttu-id="0fe6b-142">Questa operazione viene eseguita configurando l'URL (Uniform Resource Locator) di individuazione automatica tramite Lync Server Management Shell e i cmdlet **Get-CsHostingProvider** e **Set-CsHostingProvider**.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-142">This is done by configuring the Autodiscover uniform resource locator (URL) by using the Lync Server Management Shell and the cmdlets **Get-CsHostingProvider** and **Set-CsHostingProvider**.</span></span>

<span data-ttu-id="0fe6b-143">Sarà necessario raccogliere e registrare i seguenti attributi distribuiti:</span><span class="sxs-lookup"><span data-stu-id="0fe6b-143">You will need to collect and record the following deployed attributes:</span></span>

  - <span data-ttu-id="0fe6b-144">In Lync Server Management Shell digitare</span><span class="sxs-lookup"><span data-stu-id="0fe6b-144">From the Lync Server Management Shell, type</span></span>
    
        Get-CsHostingProvider

  - <span data-ttu-id="0fe6b-145">Nei risultati trovare il provider online con l'attributo **ProxyFqdn**.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-145">In the results, find the online provider with the attribute **ProxyFQDN**.</span></span> <span data-ttu-id="0fe6b-146">Ad esempio, sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="0fe6b-146">For example, sipfed.online.lync.com</span></span>

  - <span data-ttu-id="0fe6b-147">Registrare il valore di ProxyFQDN</span><span class="sxs-lookup"><span data-stu-id="0fe6b-147">Record the value of the ProxyFQDN</span></span>

  - <span data-ttu-id="0fe6b-148">Abilitare la Federazione nel pannello di controllo di Lync Server locale, consentendo la Federazione con il provider online</span><span class="sxs-lookup"><span data-stu-id="0fe6b-148">Enable federation in the on-premise Lync Server Control Panel, allowing federation with the online provider</span></span>

  - <span data-ttu-id="0fe6b-149">Abilitare la Federazione per il provider online.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-149">Enable federation for the online provider.</span></span> <span data-ttu-id="0fe6b-150">Per impostazione predefinita, tutti gli utenti online sono abilitati per la Federazione del dominio e possono comunicare con tutti i domini</span><span class="sxs-lookup"><span data-stu-id="0fe6b-150">By default, all online users are enabled for domain federation and can communicate with all domains</span></span>

  - <span data-ttu-id="0fe6b-151">Se si definiscono i domini bloccati e consentiti, determinare i domini che verranno esplicitamente consentiti o bloccati esplicitamente</span><span class="sxs-lookup"><span data-stu-id="0fe6b-151">If you will define blocked and allowed domains, determine the domains that you will explicitly allow or explicitly block</span></span>

  - <span data-ttu-id="0fe6b-152">Per la Federazione online, è necessario pianificare le eccezioni del firewall, i certificati e l'host DNS (A o AAAA, se si usano i record IPv6).</span><span class="sxs-lookup"><span data-stu-id="0fe6b-152">For online federation, you must plan for firewall exceptions, certificates and DNS host (A or AAAA, if using IPv6) records.</span></span> <span data-ttu-id="0fe6b-153">È inoltre necessario configurare i criteri federativi.</span><span class="sxs-lookup"><span data-stu-id="0fe6b-153">Additionally, you must configure federation policies.</span></span> <span data-ttu-id="0fe6b-154">Per informazioni dettagliate, vedere [pianificazione per Lync server 2013 e Office Communications Server Federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span><span class="sxs-lookup"><span data-stu-id="0fe6b-154">For details, see [Planning for Lync Server 2013 and Office Communications Server federation](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

