---
title: 'Lync Server 2013: Requisiti DNS per gli URL semplici'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for simple URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425874(v=OCS.15)
ms:contentKeyID: 48183912
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a05b5e5afc645c9219d02c8a551e4c0af9d93b0
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="ad581-102">Requisiti DNS per gli URL semplici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ad581-102">DNS requirements for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad581-103">_**Argomento Ultima modifica:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="ad581-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="ad581-104">Lync Server 2013 supporta gli URL semplici, che semplificano le riunioni di partecipazione per gli utenti e rendono più semplice l'accesso agli strumenti di amministrazione di Lync Server per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="ad581-104">Lync Server 2013 supports simple URLs, which make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span> <span data-ttu-id="ad581-105">Per informazioni dettagliate sugli URL semplici, vedere [pianificazione di URL semplici in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="ad581-105">For details about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span></span>

<span data-ttu-id="ad581-106">Lync Server supporta i tre semplici URL seguenti: Meet, Dial-in e admin. È necessario configurare URL semplici per riunioni e accesso esterno e l'URL semplice per l'amministratore è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="ad581-106">Lync Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="ad581-107">I record DNS (Domain Name System) necessari per supportare gli URL semplici dipendono dal modo in cui sono stati definiti questi URL semplici e se si vuole supportare il ripristino di emergenza per gli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="ad581-107">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span>

<div>

## <a name="simple-url-option-1"></a><span data-ttu-id="ad581-108">Opzione semplice URL 1</span><span class="sxs-lookup"><span data-stu-id="ad581-108">Simple URL Option 1</span></span>

<span data-ttu-id="ad581-109">Nell'opzione 1 si crea un nuovo URL di base per ogni URL semplice.</span><span class="sxs-lookup"><span data-stu-id="ad581-109">In Option 1, you create a new base URL for each simple URL.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="ad581-110">Quando un utente fa clic su un collegamento a una riunione URL semplice, il server che il record DNS risolve per determinare il software client corretto per l'avvio.</span><span class="sxs-lookup"><span data-stu-id="ad581-110">When a user clicks a simple URL meeting link, the server that the DNS A record resolves to determines the correct client software to start.</span></span> <span data-ttu-id="ad581-111">Dopo l'avvio del software client, la comunicazione viene comunicata automaticamente con il pool in cui è ospitata la conferenza.</span><span class="sxs-lookup"><span data-stu-id="ad581-111">After the client software is started, it automatically communicates with the pool where the conference is hosted.</span></span> <span data-ttu-id="ad581-112">In questo modo, gli utenti vengono indirizzati al server appropriato per il contenuto della riunione, indipendentemente dal server o dal pool in cui vengono risolti i record DNS dell'URL semplice.</span><span class="sxs-lookup"><span data-stu-id="ad581-112">This way, users are directed to the appropriate server for meeting content no matter which server or pool the simple URL DNS A records resolve to.</span></span>



</div>

### <a name="simple-url-option-1"></a><span data-ttu-id="ad581-113">Opzione semplice URL 1</span><span class="sxs-lookup"><span data-stu-id="ad581-113">Simple URL Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad581-114"><strong>URL semplice</strong></span><span class="sxs-lookup"><span data-stu-id="ad581-114"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="ad581-115"><strong>Esempio</strong></span><span class="sxs-lookup"><span data-stu-id="ad581-115"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad581-116">Soddisfano</span><span class="sxs-lookup"><span data-stu-id="ad581-116">Meet</span></span></p></td>
<td><p><span data-ttu-id="ad581-117">https://meet.contoso.com, https://meet.fabrikam.come così via (uno per ogni dominio SIP nell'organizzazione)</span><span class="sxs-lookup"><span data-stu-id="ad581-117">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad581-118">Accesso esterno</span><span class="sxs-lookup"><span data-stu-id="ad581-118">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad581-119">Admin</span><span class="sxs-lookup"><span data-stu-id="ad581-119">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ad581-120">Se si usa l'opzione 1, è necessario definire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ad581-120">If you use Option 1, you must define the following:</span></span>

  - <span data-ttu-id="ad581-121">Per ogni URL semplice di riunione, è necessario un record DNS che risolva l'URL per l'indirizzo IP del direttore, se ne è stato distribuito uno.</span><span class="sxs-lookup"><span data-stu-id="ad581-121">For each Meet simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="ad581-122">In caso contrario, deve essere risolto nell'indirizzo IP del bilanciamento del carico di un pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="ad581-122">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="ad581-123">Se non è stato distribuito un pool e si usa una distribuzione di server Standard Edition, il record DNS deve essere risolto nell'indirizzo IP di un server standard dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ad581-123">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>
    
    <span data-ttu-id="ad581-124">Se si hanno più domini SIP nell'organizzazione e si usa questa opzione, è necessario creare URL semplici per ogni dominio SIP ed è necessario un record DNS per ogni URL semplice di riunione.</span><span class="sxs-lookup"><span data-stu-id="ad581-124">If you have more than one SIP domain in your organization and you use this option, you must create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="ad581-125">Se ad esempio sono presenti sia contoso.com che fabrikam.com, verranno creati record DNS per entrambi https://meet.contoso.com e. https://meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ad581-125">For example, if you have both contoso.com and fabrikam.com, you will create DNS A records for both https://meet.contoso.com and https://meet.fabrikam.com.</span></span>
    
    <span data-ttu-id="ad581-126">In alternativa, se si hanno più domini SIP e si vuole minimizzare il record DNS e i requisiti di certificato per questi URL semplici, usare l'opzione 3 come descritto più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ad581-126">Alternatively, if you have multiple SIP domains and you want to minimize the DNS record and certificate requirements for these simple URLs, use Option 3 as described later in this topic.</span></span>

  - <span data-ttu-id="ad581-127">Per l'URL semplice con accesso esterno, è necessario un record DNS che risolva l'URL per l'indirizzo IP del direttore, se ne è stato distribuito uno.</span><span class="sxs-lookup"><span data-stu-id="ad581-127">For the Dial-in simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="ad581-128">In caso contrario, deve essere risolto nell'indirizzo IP del bilanciamento del carico di un pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="ad581-128">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="ad581-129">Se non è stato distribuito un pool e si usa una distribuzione di server Standard Edition, il record DNS deve essere risolto nell'indirizzo IP di un server standard dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ad581-129">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

  - <span data-ttu-id="ad581-130">L'URL semplice amministratore è solo interno.</span><span class="sxs-lookup"><span data-stu-id="ad581-130">The Admin simple URL is internal only.</span></span> <span data-ttu-id="ad581-131">Richiede un record DNS che risolva l'URL per l'indirizzo IP del direttore, se ne è stato distribuito uno.</span><span class="sxs-lookup"><span data-stu-id="ad581-131">It requires a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed.</span></span> <span data-ttu-id="ad581-132">In caso contrario, deve essere risolto nell'indirizzo IP del bilanciamento del carico di un pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="ad581-132">Otherwise, it should resolve to the IP address of the load balancer of a Front End pool.</span></span> <span data-ttu-id="ad581-133">Se non è stato distribuito un pool e si usa una distribuzione di server Standard Edition, il record DNS deve essere risolto nell'indirizzo IP di un server standard dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ad581-133">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

</div>

<div>

## <a name="simple-url-option-2"></a><span data-ttu-id="ad581-134">Opzione semplice URL 2</span><span class="sxs-lookup"><span data-stu-id="ad581-134">Simple URL Option 2</span></span>

<span data-ttu-id="ad581-135">Con l'opzione 2, gli URL semplici Meet, Dial-in e admin hanno tutti un URL di base comune, ad esempio lync.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ad581-135">With Option 2, the Meet, Dial-in, and Admin simple URLs all have a common base URL, such as lync.contoso.com.</span></span> <span data-ttu-id="ad581-136">Di conseguenza, è necessario un solo record DNS per questi URL semplici, che risolve lync.contoso.com nell'indirizzo IP di un pool di Director o di un pool di front-end.</span><span class="sxs-lookup"><span data-stu-id="ad581-136">Therefore, you need only one DNS A record for these simple URLs, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span> <span data-ttu-id="ad581-137">Se non è stato distribuito un pool e si usa una distribuzione di server Standard Edition, il record DNS deve essere risolto nell'indirizzo IP di un server standard dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ad581-137">If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

<span data-ttu-id="ad581-138">Tieni presente che se si hanno più domini SIP nell'organizzazione, è comunque necessario creare URL semplici per ogni dominio SIP ed è necessario un record DNS per ogni URL semplice di riunione.</span><span class="sxs-lookup"><span data-stu-id="ad581-138">Note that if you have more than one SIP domain in your organization, you must still create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="ad581-139">In questo esempio, mentre tre URL semplici sono tutti basati su lync.contoso.com, viene configurato un URL di riunione semplice aggiuntivo per fabrikam.com con un URL di base diverso.</span><span class="sxs-lookup"><span data-stu-id="ad581-139">In this example, while three simple URLs are all based on lync.contoso.com, an additional Meet simple URL for fabrikam.com is set up with a different base URL.</span></span> <span data-ttu-id="ad581-140">In questo esempio è necessario creare record DNS per entrambi https://lync.contoso.com e. https://lync.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="ad581-140">In this example, you must create DNS A records for both https://lync.contoso.com and https://lync.fabrikam.com.</span></span> <span data-ttu-id="ad581-141">L'opzione semplice URL 3 Mostra un altro modo per gestire i record di denominazione e DNS se si hanno più domini SIP.</span><span class="sxs-lookup"><span data-stu-id="ad581-141">Simple URL Option 3 shows another way to handle naming and DNS A records if you have multiple SIP domains.</span></span>

### <a name="simple-url-option-2"></a><span data-ttu-id="ad581-142">Opzione semplice URL 2</span><span class="sxs-lookup"><span data-stu-id="ad581-142">Simple URL Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad581-143"><strong>URL semplice</strong></span><span class="sxs-lookup"><span data-stu-id="ad581-143"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="ad581-144"><strong>Esempio</strong></span><span class="sxs-lookup"><span data-stu-id="ad581-144"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad581-145">Soddisfano</span><span class="sxs-lookup"><span data-stu-id="ad581-145">Meet</span></span></p></td>
<td><p><span data-ttu-id="ad581-146">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meete così via (uno per ogni dominio SIP nell'organizzazione)</span><span class="sxs-lookup"><span data-stu-id="ad581-146">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad581-147">Accesso esterno</span><span class="sxs-lookup"><span data-stu-id="ad581-147">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad581-148">Admin</span><span class="sxs-lookup"><span data-stu-id="ad581-148">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a><span data-ttu-id="ad581-149">Opzione semplice URL 3</span><span class="sxs-lookup"><span data-stu-id="ad581-149">Simple URL Option 3</span></span>

<span data-ttu-id="ad581-150">L'opzione 3 è molto utile se si hanno molti domini SIP e si vuole che dispongano di URL semplici separati, ma che si vogliano minimizzare il record DNS e i requisiti di certificato per questi URL semplici.</span><span class="sxs-lookup"><span data-stu-id="ad581-150">Option 3 is most useful if you have many SIP domains, and you want them to have separate simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span> <span data-ttu-id="ad581-151">In questo esempio è necessario un solo record DNS, che risolve lync.contoso.com con l'indirizzo IP di un pool di Director o di un pool di front-end.</span><span class="sxs-lookup"><span data-stu-id="ad581-151">In this example, you need only one DNS A record, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span>

### <a name="simple-url-option-3"></a><span data-ttu-id="ad581-152">Opzione semplice URL 3</span><span class="sxs-lookup"><span data-stu-id="ad581-152">Simple URL Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad581-153"><strong>URL semplice</strong></span><span class="sxs-lookup"><span data-stu-id="ad581-153"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="ad581-154"><strong>Esempio</strong></span><span class="sxs-lookup"><span data-stu-id="ad581-154"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad581-155">Soddisfano</span><span class="sxs-lookup"><span data-stu-id="ad581-155">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad581-156">Accesso esterno</span><span class="sxs-lookup"><span data-stu-id="ad581-156">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad581-157">Admin</span><span class="sxs-lookup"><span data-stu-id="ad581-157">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="ad581-158">Opzione di ripristino di emergenza per URL semplici</span><span class="sxs-lookup"><span data-stu-id="ad581-158">Disaster Recovery Option for Simple URLs</span></span>

<span data-ttu-id="ad581-159">Se si hanno più siti che contengono pool Front-end e il provider DNS supporta GeoDNS, è possibile configurare i record DNS per gli URL semplici per supportare il ripristino di emergenza, in modo che le funzionalità degli URL semplici continuino anche se si abbassa un intero pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="ad581-159">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="ad581-160">Questa funzionalità di ripristino di emergenza supporta gli URL semplici di riunione e accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="ad581-160">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="ad581-161">Per configurare la configurazione, creare due indirizzi di GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="ad581-161">To configure this, create two GeoDNS addresses.</span></span> <span data-ttu-id="ad581-162">Ogni indirizzo contiene due record DNS A o CNAME che vengono risolti in due pool combinati per scopi di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="ad581-162">Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes.</span></span> <span data-ttu-id="ad581-163">Un indirizzo GeoDNS viene usato per l'accesso interno e viene risolto nell'indirizzo IP di FQDN Web interno o di bilanciamento del carico per i due pool.</span><span class="sxs-lookup"><span data-stu-id="ad581-163">One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="ad581-164">L'altro indirizzo GeoDNS viene usato per l'accesso esterno e si risolve nell'FQDN Web esterno o nell'indirizzo IP del bilanciamento del carico per i due pool.</span><span class="sxs-lookup"><span data-stu-id="ad581-164">The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="ad581-165">Di seguito è riportato un esempio per l'URL semplice Meet, che usa i nomi di dominio completi per i pool.</span><span class="sxs-lookup"><span data-stu-id="ad581-165">The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span>

   ```console
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```console
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

<span data-ttu-id="ad581-166">Crea quindi i record CNAME che risolvono l'URL semplice di riunione (ad esempio meet.contoso.com) ai due indirizzi di GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="ad581-166">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="ad581-167">Se la rete usa <EM>hairpinning</EM> (instradando tutto il traffico di URL semplice tramite il collegamento esterno, incluso il traffico proveniente dall'interno dell'organizzazione), è possibile configurare l'indirizzo di GeoDNS esterno e risolvere l'URL semplice che si incontra solo per l'indirizzo esterno.</span><span class="sxs-lookup"><span data-stu-id="ad581-167">If your network uses <EM>hairpinning</EM> (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>



</div>

<span data-ttu-id="ad581-168">Quando usi questo metodo, puoi configurare ogni indirizzo di GeoDNS in modo da usare un metodo Round Robin per distribuire le richieste ai due pool oppure per connetterti principalmente a un pool, ad esempio il pool situato geograficamente più vicino, e usare l'altro pool solo in caso di errore di connettività.</span><span class="sxs-lookup"><span data-stu-id="ad581-168">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span>

<span data-ttu-id="ad581-169">È possibile configurare la stessa configurazione per l'URL semplice con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="ad581-169">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="ad581-170">A questo scopo, crea altri record come quelli nell'esempio precedente, sostituendo `dialin` per `meet` i record DNS.</span><span class="sxs-lookup"><span data-stu-id="ad581-170">To do so, create additional records like those in the previous example, substituting `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="ad581-171">Per l'URL semplice amministratore, usa una delle tre opzioni elencate in precedenza in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="ad581-171">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="ad581-172">Una volta configurata questa configurazione, è necessario usare un'applicazione di monitoraggio per configurare il monitoraggio HTTP per la visualizzazione degli errori.</span><span class="sxs-lookup"><span data-stu-id="ad581-172">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="ad581-173">Per l'accesso esterno, monitorare per assicurarsi che HTTPS ottenere le richieste di individuazione automatica per l'FQDN Web esterno o l'indirizzo IP del bilanciamento del carico per i due pool abbia successo.</span><span class="sxs-lookup"><span data-stu-id="ad581-173">For external access, monitor to make sure that HTTPS GET autodiscovery requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="ad581-174">Ad esempio, le richieste seguenti non devono contenere alcuna intestazione **Accept** e devono restituire **200 OK**.</span><span class="sxs-lookup"><span data-stu-id="ad581-174">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="ad581-175">Per l'accesso interno, è necessario monitorare la porta 5061 nell'FQDN Web interno o nell'indirizzo IP del bilanciamento del carico per i due pool.</span><span class="sxs-lookup"><span data-stu-id="ad581-175">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools.</span></span> <span data-ttu-id="ad581-176">Se vengono rilevati errori di connettività, il VIP per questi pool deve chiudere le porte 80, 443 e 444.</span><span class="sxs-lookup"><span data-stu-id="ad581-176">If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 444.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

