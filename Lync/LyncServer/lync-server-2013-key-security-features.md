---
title: 'Lync Server 2013: caratteristiche di sicurezza principali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53a6d9e23442cb127f0f08849e18f1d63bae76d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="f968b-102">Caratteristiche di sicurezza chiave in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f968b-102">Key security features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f968b-103">_**Argomento Ultima modifica:** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="f968b-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="f968b-104">Lync Server 2013 include diverse funzionalità di sicurezza, tra cui l'autenticazione da server a server, il controllo dell'accesso basato sui ruoli e lo spazio di archiviazione centralizzato dei dati di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f968b-104">Lync Server 2013 includes several security features, including server-to-server authentication, role-based access control, and centralized storage of configuration data.</span></span>

<span data-ttu-id="f968b-105">Questo articolo offre una panoramica di alto livello sulla sicurezza di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f968b-105">This article provides a high level overview of Lync Server 2013 security.</span></span>

<div>

## <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="f968b-106">Caratteristiche di sicurezza chiave in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f968b-106">Key Security Features in Lync Server 2013</span></span>

<span data-ttu-id="f968b-107">La sicurezza è un argomento molto ampio.</span><span class="sxs-lookup"><span data-stu-id="f968b-107">Security is a very broad topic.</span></span> <span data-ttu-id="f968b-108">La sicurezza raggiunge tutte le funzionalità di Lync Server 2013, nonché database, servizi e hardware che costituiscono un ecosistema Lync.</span><span class="sxs-lookup"><span data-stu-id="f968b-108">Security reaches across every feature of Lync Server 2013 as well as databases, services, and hardware that make up a Lync ecosystem.</span></span> <span data-ttu-id="f968b-109">In questo articolo vengono illustrate alcune delle funzionalità di Lync Server 2013, in particolare progettate per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f968b-109">This article outlines some of the features in Lync Server 2013 in particular that are designed for security.</span></span>

<div>

## <a name="planning-and-design-tools"></a><span data-ttu-id="f968b-110">Strumenti di pianificazione e progettazione</span><span class="sxs-lookup"><span data-stu-id="f968b-110">Planning and Design Tools</span></span>

<span data-ttu-id="f968b-111">Lync Server 2013 offre due strumenti per semplificare la pianificazione e la progettazione e per ridurre la possibilità di configurare automaticamente i componenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f968b-111">Lync Server 2013 provides two tools to facilitate planning and design and to reduce the chance of misconfiguring Lync Server components.</span></span>

  - <span data-ttu-id="f968b-112">**Lo strumento di pianificazione della topologia** automatizza gran parte del processo di progettazione della topologia.</span><span class="sxs-lookup"><span data-stu-id="f968b-112">**Topology Planning Tool** automates much of the topology design process.</span></span> <span data-ttu-id="f968b-113">È possibile esportare i risultati dello strumento di pianificazione in Generatore di topologia, che è lo strumento necessario per installare ogni server in cui è in uso Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f968b-113">You can export the results from the Planning Tool to Topology Builder, which is the tool that is required to install each server running Lync Server 2013.</span></span>

  - <span data-ttu-id="f968b-114">**Generatore di topologie** archivia tutte le informazioni di configurazione nell'Central Management store.</span><span class="sxs-lookup"><span data-stu-id="f968b-114">**Topology Builder** stores all configuration information in the Central Management store.</span></span>

<span data-ttu-id="f968b-115">Per informazioni dettagliate su questi strumenti, vedere [pianificazione di Lync Server 2013](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="f968b-115">For details about these tools, see [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

</div>

<div>

## <a name="central-management-store"></a><span data-ttu-id="f968b-116">Central Management store</span><span class="sxs-lookup"><span data-stu-id="f968b-116">Central Management Store</span></span>

<span data-ttu-id="f968b-117">In Lync Server 2013 i dati di configurazione relativi a server e servizi fanno parte dell'Central Management store.</span><span class="sxs-lookup"><span data-stu-id="f968b-117">In Lync Server 2013, configuration data about servers and services is part of the Central Management store.</span></span> <span data-ttu-id="f968b-118">Il Central Management store offre uno spazio di archiviazione robusto e schematizzato dei dati necessari per definire, configurare, gestire, amministrare, descrivere e gestire una distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f968b-118">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server deployment.</span></span> <span data-ttu-id="f968b-119">Convalida inoltre i dati per garantire la coerenza della configurazione.</span><span class="sxs-lookup"><span data-stu-id="f968b-119">It also validates the data to ensure configuration consistency.</span></span> <span data-ttu-id="f968b-120">Tutte le modifiche apportate ai dati di configurazione si verificano presso l'Central Management store, eliminando i problemi di "fuori sincrono".</span><span class="sxs-lookup"><span data-stu-id="f968b-120">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span>

<span data-ttu-id="f968b-121">Le copie di sola lettura dei dati vengono replicate in tutti i server della topologia, inclusi Edge Server e Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="f968b-121">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers and Survivable Branch Appliances.</span></span> <span data-ttu-id="f968b-122">La replica è gestita da un servizio che, per impostazione predefinita, viene eseguito nel contesto del servizio di rete, riducendo i diritti e le autorizzazioni a quello di un utente semplice nel computer.</span><span class="sxs-lookup"><span data-stu-id="f968b-122">Replication is managed by a service that is, by default, run under the context of the Network service, reducing the rights and permissions to that of a simple user on the computer.</span></span>

</div>

<div>

## <a name="server-to-server-authentication"></a><span data-ttu-id="f968b-123">Autenticazione da server a server</span><span class="sxs-lookup"><span data-stu-id="f968b-123">Server-to-Server Authentication</span></span>

<span data-ttu-id="f968b-124">In Lync Server 2013 l'autenticazione può essere configurata tra i server tramite il protocollo OAuth (Open Authorization).</span><span class="sxs-lookup"><span data-stu-id="f968b-124">In Lync Server 2013, authentication can be configured between servers by using the Open Authorization (OAuth) protocol.</span></span> <span data-ttu-id="f968b-125">Ad esempio, è possibile configurare Lync Server 2013 per l'autenticazione con un server in cui è in uso Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f968b-125">For example, you can configure Lync Server 2013 to authenticate with a server that is running Exchange Server 2013.</span></span> <span data-ttu-id="f968b-126">Usando il protocollo OAuth, il server Lync e il server Exchange possono considerarsi attendibili.</span><span class="sxs-lookup"><span data-stu-id="f968b-126">Using the OAuth protocol, the Lync server and the Exchange server can trust each other.</span></span> <span data-ttu-id="f968b-127">Questo consente di integrare i prodotti in modo uniforme.</span><span class="sxs-lookup"><span data-stu-id="f968b-127">This provides the ability to integrate the products in a seamless manner.</span></span> <span data-ttu-id="f968b-128">Per informazioni dettagliate, vedere [gestione dell'autenticazione server-Server (OAuth) e delle applicazioni partner in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="f968b-128">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a><span data-ttu-id="f968b-129">Interfaccia di gestione basata su Windows PowerShell e gestione basata sul Web</span><span class="sxs-lookup"><span data-stu-id="f968b-129">Windows PowerShell-based management and Web-based Management Interface</span></span>

<span data-ttu-id="f968b-130">Lync Server 2013 offre una potente interfaccia di gestione, basata sull'interfaccia della riga di comando di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f968b-130">Lync Server 2013 provides a powerful management interface, built on the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="f968b-131">Include i cmdlet per la gestione della sicurezza e le funzionalità di sicurezza di Windows PowerShell sono abilitate per impostazione predefinita in modo che gli utenti non possano eseguire facilmente o inconsapevolmente gli script.</span><span class="sxs-lookup"><span data-stu-id="f968b-131">It includes cmdlets for managing security, and Windows PowerShell security features are enabled by default so that users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="f968b-132">Questo significa che le impostazioni predefinite del software sono impostate in modo da aiutare automaticamente a massimizzare la sicurezza e ridurre i viali di attacco.</span><span class="sxs-lookup"><span data-stu-id="f968b-132">This means that the software defaults are set to automatically help maximize security and reduce the avenues of attack.</span></span> <span data-ttu-id="f968b-133">Per informazioni dettagliate sul supporto per la gestione di Windows PowerShell in Lync Server 2013, vedere [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="f968b-133">For details about Windows PowerShell management support in Lync Server 2013, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="role-based-access-control-rbac"></a><span data-ttu-id="f968b-134">Controllo di accesso basato sui ruoli (RBAC)</span><span class="sxs-lookup"><span data-stu-id="f968b-134">Role-Based Access Control (RBAC)</span></span>

<span data-ttu-id="f968b-135">Microsoft Lync Server 2013 fornisce il controllo di accesso basato sui ruoli (RBAC) per consentire di delegare le attività amministrative mantenendo standard elevati per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f968b-135">Microsoft Lync Server 2013 provides role-based access control (RBAC) to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="f968b-136">È possibile usare RBAC per seguire il principio "privilegio minimo", in cui agli utenti vengono assegnati solo i diritti amministrativi necessari per i processi.</span><span class="sxs-lookup"><span data-stu-id="f968b-136">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative rights that their jobs require.</span></span> <span data-ttu-id="f968b-137">Lync Server 2013 introduce la possibilità di creare un nuovo ruolo e anche la possibilità di modificare un ruolo esistente.</span><span class="sxs-lookup"><span data-stu-id="f968b-137">Lync Server 2013 introduces the ability to create a new role and also the ability to modify an existing role.</span></span> <span data-ttu-id="f968b-138">Per informazioni dettagliate, vedere [pianificazione per il controllo dell'accesso basato sui ruoli in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="f968b-138">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a><span data-ttu-id="f968b-139">NAT (Network Address Translation)</span><span class="sxs-lookup"><span data-stu-id="f968b-139">Network Address Translation (NAT)</span></span>

<span data-ttu-id="f968b-140">Lync Server 2013 non supporta l'uso di NAT (Network Address Translation) nell'interfaccia interna di Edge Server, ma supporta l'inserimento dell'interfaccia esterna di Access Edge service, Web Conferencing Edge service e A/V Edge service dietro un router o un firewall che esegue la traduzione di indirizzi di rete per le topologie di server perimetrali consolidate singole e in scala.</span><span class="sxs-lookup"><span data-stu-id="f968b-140">Lync Server 2013 does not support the use of network address translation (NAT) on the internal interface of the Edge Server, but it does support placing the external interface of the Access Edge service, Web Conferencing Edge service, and A/V Edge service behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span> <span data-ttu-id="f968b-141">Più Edge Server dietro un bilanciamento del carico hardware non può usare NAT.</span><span class="sxs-lookup"><span data-stu-id="f968b-141">Multiple Edge Servers behind a hardware load balancer cannot use NAT.</span></span> <span data-ttu-id="f968b-142">Se più Edge Server usano NAT sulle loro interfacce esterne, è necessario il bilanciamento del carico DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="f968b-142">If multiple Edge Servers use NAT on their external interfaces, Domain Name System (DNS) load balancing is required.</span></span> <span data-ttu-id="f968b-143">A sua volta, l'uso del bilanciamento del carico DNS consente di ridurre il numero di indirizzi IP pubblici per ogni server perimetrale in un pool di Edge Server.</span><span class="sxs-lookup"><span data-stu-id="f968b-143">In turn, using DNS load balancing allows you to reduce the number of public IP addresses per Edge Server in an Edge Server pool.</span></span> <span data-ttu-id="f968b-144">Per informazioni dettagliate, vedere[pianificazione per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="f968b-144">For details, see[Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f968b-145">Se si esegue la Federazione con le aziende che hanno una distribuzione di Microsoft Office Communications Server 2007 ed è necessario usare audio/video tra l'organizzazione e l'organizzazione federata, i requisiti della porta saranno quelli della versione precedente di Edge Server distribuiti.</span><span class="sxs-lookup"><span data-stu-id="f968b-145">If you federate with enterprises that have a Microsoft Office Communications Server 2007 deployment and you need to use audio/video between your enterprise and the federated enterprise, the port requirements will be those for the older version of the Edge Servers that are deployed.</span></span> <span data-ttu-id="f968b-146">Ad esempio, gli intervalli di porta necessari per le versioni precedenti devono essere aperti per entrambe le aziende fino a quando il partner federativo non aggiorna i propri Edge Server a Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f968b-146">For example, the port ranges required for those older versions must be opened for both enterprises until the federated partner upgrades its Edge Servers to Lync Server 2013.</span></span> <span data-ttu-id="f968b-147">A questo punto, i requisiti della porta possono essere rivisti e ridotti in base alla nuova configurazione.</span><span class="sxs-lookup"><span data-stu-id="f968b-147">At that time, the port requirements can be reviewed and reduced according to the new configuration.</span></span>



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a><span data-ttu-id="f968b-148">Certificati semplificati per Edge Server</span><span class="sxs-lookup"><span data-stu-id="f968b-148">Simplified Certificates for Edge Servers</span></span>

<span data-ttu-id="f968b-149">La distribuzione guidata può automaticamente popolare i nomi dei soggetti (SNs) e i nomi alternativi oggetto (SANs), riducendo la possibilità di includere voci non necessarie e potenzialmente non sicure.</span><span class="sxs-lookup"><span data-stu-id="f968b-149">The Deployment Wizard can automatically populate subject names (SNs) and subject alternative names (SANs), reducing the possibility of including unnecessary and potentially unsecure entries.</span></span>

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a><span data-ttu-id="f968b-150">Ciclo di vita per lo sviluppo della sicurezza (SDL) Trustworthy Computing</span><span class="sxs-lookup"><span data-stu-id="f968b-150">Trustworthy Computing Security Development Lifecycle (SDL)</span></span>

<span data-ttu-id="f968b-151">Lync Server 2013 è progettato e sviluppato in conformità con il ciclo di vita Microsoft Trustworthy Computing Security Development Lifecycle (SDL), <http://go.microsoft.com/fwlink/?linkid=68761>descritto in.</span><span class="sxs-lookup"><span data-stu-id="f968b-151">Lync Server 2013 is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at <http://go.microsoft.com/fwlink/?linkid=68761>.</span></span>

  - <span data-ttu-id="f968b-152">\*\*\*\*   In modo affidabile in base alla progettazione il primo passaggio per creare un sistema di comunicazioni unificate più sicuro consiste nel progettare modelli di minacce e testare ogni funzionalità come è stata progettata.</span><span class="sxs-lookup"><span data-stu-id="f968b-152">**Trustworthy by Design**   The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed.</span></span> <span data-ttu-id="f968b-153">Microsoft esegue inoltre test al di fuori del comportamento progettato per individuare le vulnerabilità di sicurezza derivanti da un comportamento del prodotto imprevisto.</span><span class="sxs-lookup"><span data-stu-id="f968b-153">In addition, Microsoft performs testing outside of the designed behavior in order to find security vulnerabilities resulting from unexpected product behavior.</span></span> <span data-ttu-id="f968b-154">Diversi miglioramenti relativi alla sicurezza sono stati integrati nel processo e nelle pratiche di codifica.</span><span class="sxs-lookup"><span data-stu-id="f968b-154">Multiple security-related improvements were built into the coding process and practices.</span></span> <span data-ttu-id="f968b-155">Gli strumenti della fase di compilazione rilevano sovraccarichi del buffer e altre potenziali minacce alla sicurezza prima che il codice venga archiviato nel prodotto finale.</span><span class="sxs-lookup"><span data-stu-id="f968b-155">Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product.</span></span> <span data-ttu-id="f968b-156">Ovviamente, è impossibile progettare contro tutte le minacce alla sicurezza sconosciute.</span><span class="sxs-lookup"><span data-stu-id="f968b-156">Of course, it is impossible to design against all unknown security threats.</span></span> <span data-ttu-id="f968b-157">Nessun sistema può garantire una protezione completa.</span><span class="sxs-lookup"><span data-stu-id="f968b-157">No system can guarantee complete security.</span></span> <span data-ttu-id="f968b-158">Tuttavia, poiché lo sviluppo del prodotto ha abbracciato i principi di progettazione sicuri fin dall'inizio, Lync Server 2013 incorpora tecnologie di sicurezza standard del settore come parte fondamentale della sua architettura.</span><span class="sxs-lookup"><span data-stu-id="f968b-158">However, because product development embraced secure design principles from the start, Lync Server 2013 incorporates industry standard security technologies as a fundamental part of its architecture.</span></span>

  - <span data-ttu-id="f968b-159">**Trustworthy per**   impostazione predefinita per impostazione predefinita, le comunicazioni di rete in Lync Server 2013 sono crittografate.</span><span class="sxs-lookup"><span data-stu-id="f968b-159">**Trustworthy by Default**   By default, network communications in Lync Server 2013 are encrypted.</span></span> <span data-ttu-id="f968b-160">Poiché tutti i server usano i certificati e l'autenticazione Kerberos, TLS, Secure Real-Time Transport Protocol (SRTP) e altre tecniche di crittografia standard del settore, tra cui la crittografia AES (Advanced Encryption Standard) di 128 bit, praticamente tutti i Lync I dati del server sono protetti in rete.</span><span class="sxs-lookup"><span data-stu-id="f968b-160">Because all servers use certificates and Kerberos authentication, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 128-bit Advanced Encryption Standard (AES) encryption, virtually all Lync Server data is protected on the network.</span></span> <span data-ttu-id="f968b-161">Il controllo di accesso basato sui ruoli consente inoltre di distribuire server che esegue Lync Server 2013 in modo che ogni ruolo del server esegua solo i servizi e disponga solo delle autorizzazioni correlate a tali servizi, che sono appropriate per il ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="f968b-161">In addition, role-based access control makes it possible to deploy servers running Lync Server 2013 so that each server role runs only the services, and has only the permissions related to those services, that are appropriate for the server role.</span></span>

  - <span data-ttu-id="f968b-162">**Attendibile tramite distribuzione**   tutta la documentazione di Lync Server 2013 include le procedure consigliate e le raccomandazioni per determinare e configurare i livelli di sicurezza ottimali per la distribuzione e valutare i rischi per la sicurezza dell'attivazione delle opzioni non predefinite.</span><span class="sxs-lookup"><span data-stu-id="f968b-162">**Trustworthy by Deployment**   All Lync Server 2013 documentation includes best practices and recommendations to help you determine and configure the optimal security levels for your deployment and assess the security risks of activating non-default options.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

