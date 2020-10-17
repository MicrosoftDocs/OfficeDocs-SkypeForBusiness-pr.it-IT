---
title: 'Lync Server 2013: requisiti DNS per gli URL semplici'
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
ms.openlocfilehash: 98db338c48bbb764aefe3d5cab4bcba58b2b23c4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501373"
---
# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="3072e-102">Requisiti DNS per gli URL semplici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3072e-102">DNS requirements for simple URLs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3072e-103">_**Ultimo argomento modificato:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="3072e-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="3072e-104">Lync Server 2013 supporta gli URL semplici, che rendono più semplice partecipare alle riunioni per gli utenti e semplificare gli strumenti di amministrazione di Lync Server per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="3072e-104">Lync Server 2013 supports simple URLs, which make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span> <span data-ttu-id="3072e-105">Per informazioni dettagliate sugli URL semplici, vedere [Planning for Simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="3072e-105">For details about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span></span>

<span data-ttu-id="3072e-106">Lync Server supporta i tre URL semplici seguenti: Meet, Dial-in e admin. È necessario configurare gli URL semplici per gli incontri e l'accesso esterno e l'URL semplice di amministrazione è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="3072e-106">Lync Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="3072e-107">I record DNS (Domain Name System) necessari per supportare gli URL semplici dipendono da come sono stati definiti gli URL e dall'eventuale impostazione del supporto del ripristino di emergenza per gli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="3072e-107">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span>

<div>

## <a name="simple-url-option-1"></a><span data-ttu-id="3072e-108">Opzione 1 per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="3072e-108">Simple URL Option 1</span></span>

<span data-ttu-id="3072e-109">Nell'opzione 1 viene creato un nuovo URL di base per ogni URL semplice.</span><span class="sxs-lookup"><span data-stu-id="3072e-109">In Option 1, you create a new base URL for each simple URL.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="3072e-p103">Quando un utente fa clic sul collegamento di una riunione con URL semplice, il server in cui viene risolto il record A DNS determina il software client corretto da avviare. Dopo l'avvio, il software client comunica automaticamente con il pool in cui è ospitata la conferenza. In questo modo, gli utenti vengono indirizzati al server appropriato per il contenuto della riunione, indipendentemente dal server o dal pool in cui vengono risolti i record A DNS degli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="3072e-p103">When a user clicks a simple URL meeting link, the server that the DNS A record resolves to determines the correct client software to start. After the client software is started, it automatically communicates with the pool where the conference is hosted. This way, users are directed to the appropriate server for meeting content no matter which server or pool the simple URL DNS A records resolve to.</span></span>



</div>

### <a name="simple-url-option-1"></a><span data-ttu-id="3072e-113">Opzione 1 per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="3072e-113">Simple URL Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3072e-114"><strong>URL semplice</strong></span><span class="sxs-lookup"><span data-stu-id="3072e-114"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="3072e-115"><strong>Esempio</strong></span><span class="sxs-lookup"><span data-stu-id="3072e-115"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3072e-116">Soddisfare</span><span class="sxs-lookup"><span data-stu-id="3072e-116">Meet</span></span></p></td>
<td><p><span data-ttu-id="3072e-117">https://meet.contoso.comhttps://meet.fabrikam.come così via (uno per ogni dominio SIP dell'organizzazione)</span><span class="sxs-lookup"><span data-stu-id="3072e-117">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3072e-118">Accesso esterno</span><span class="sxs-lookup"><span data-stu-id="3072e-118">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3072e-119">Amministratore</span><span class="sxs-lookup"><span data-stu-id="3072e-119">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3072e-120">Se si utilizza l'opzione 1, è necessario definire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3072e-120">If you use Option 1, you must define the following:</span></span>

  - <span data-ttu-id="3072e-p104">Per ogni URL semplice riunione, è necessario un record A DNS che risolva l'URL nell'indirizzo IP del Director, se ne è stato distribuito uno, altrimenti nell'indirizzo IP del servizio di bilanciamento del carico di un pool Front End. Se non è stato distribuito un pool e si utilizza una distribuzione di server Standard Edition, il record A DNS deve risolversi nell'indirizzo IP di un server Standard Edition dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3072e-p104">For each Meet simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>
    
    <span data-ttu-id="3072e-124">Se nell'organizzazione sono presenti più domini SIP e si utilizza questa opzione, è necessario creare URL semplici riunione per ogni dominio SIP e disporre di un record A DNS per ogni URL semplice riunione.</span><span class="sxs-lookup"><span data-stu-id="3072e-124">If you have more than one SIP domain in your organization and you use this option, you must create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="3072e-125">Ad esempio, se si dispone sia di contoso.com che di fabrikam.com, verranno creati record A DNS per entrambi https://meet.contoso.com e https://meet.fabrikam.com .</span><span class="sxs-lookup"><span data-stu-id="3072e-125">For example, if you have both contoso.com and fabrikam.com, you will create DNS A records for both https://meet.contoso.com and https://meet.fabrikam.com.</span></span>
    
    <span data-ttu-id="3072e-126">In alternativa, se si dispone di più domini SIP e si desidera ridurre al minimo i requisiti di record DNS e certificati per questi URL semplici, utilizzare l'opzione 3 descritta più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="3072e-126">Alternatively, if you have multiple SIP domains and you want to minimize the DNS record and certificate requirements for these simple URLs, use Option 3 as described later in this topic.</span></span>

  - <span data-ttu-id="3072e-p106">Per ogni URL semplice per accesso esterno, è necessario un record A DNS che risolva l'URL nell'indirizzo IP del Director, se ne è stato distribuito uno, altrimenti nell'indirizzo IP del servizio di bilanciamento del carico di un pool Front End. Se non è stato distribuito un pool e si utilizza una distribuzione di server Standard Edition, il record A DNS deve risolversi nell'indirizzo IP di un server Standard Edition dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3072e-p106">For the Dial-in simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

  - <span data-ttu-id="3072e-p107">L'URL semplice di amministrazione è solo per uso interno. Richiede un record A DNS che risolva l'URL nell'indirizzo IP del Director, se ne è stato distribuito uno, altrimenti nell'indirizzo IP del servizio di bilanciamento del carico di un pool Front End. Se non è stato distribuito un pool e si utilizza una distribuzione di server Standard Edition, il record A DNS deve risolversi nell'indirizzo IP di un server Standard Edition dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3072e-p107">The Admin simple URL is internal only. It requires a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

</div>

<div>

## <a name="simple-url-option-2"></a><span data-ttu-id="3072e-134">Opzione 2 per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="3072e-134">Simple URL Option 2</span></span>

<span data-ttu-id="3072e-p108">Con l'opzione 2, tutti gli URL di base riunione, per accesso esterno e di amministrazione dispongono di un URL di base comune, ad esempio lync.contoso.com. È necessario pertanto un solo record A DNS per questi URL semplici che risolva lync.contoso.com nell'indirizzo IP di un pool di server Director o di un pool Front End. Se non è stato distribuito un pool e si utilizza una distribuzione di server Standard Edition, il record A DNS deve risolversi nell'indirizzo IP di un server Standard Edition dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3072e-p108">With Option 2, the Meet, Dial-in, and Admin simple URLs all have a common base URL, such as lync.contoso.com. Therefore, you need only one DNS A record for these simple URLs, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

<span data-ttu-id="3072e-138">Si noti che se nell'organizzazione sono presenti più domini SIP, è sempre necessario creare URL semplici riunione per ogni dominio SIP e disporre di un record A DNS per ogni URL semplice riunione.</span><span class="sxs-lookup"><span data-stu-id="3072e-138">Note that if you have more than one SIP domain in your organization, you must still create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="3072e-139">In questo esempio tre URL semplici sono tutti basati su lync.contoso.com, mentre un URL semplice riunione aggiuntivo per fabrikam.com è configurato con un URL di base diverso.</span><span class="sxs-lookup"><span data-stu-id="3072e-139">In this example, while three simple URLs are all based on lync.contoso.com, an additional Meet simple URL for fabrikam.com is set up with a different base URL.</span></span> <span data-ttu-id="3072e-140">In questo esempio, è necessario creare record DNS A per entrambi https://lync.contoso.com e https://lync.fabrikam.com .</span><span class="sxs-lookup"><span data-stu-id="3072e-140">In this example, you must create DNS A records for both https://lync.contoso.com and https://lync.fabrikam.com.</span></span> <span data-ttu-id="3072e-141">L'opzione 3 per gli URL semplici consente di gestire in un altro modo ancora la denominazione e i record A DNS in presenza di più domini SIP.</span><span class="sxs-lookup"><span data-stu-id="3072e-141">Simple URL Option 3 shows another way to handle naming and DNS A records if you have multiple SIP domains.</span></span>

### <a name="simple-url-option-2"></a><span data-ttu-id="3072e-142">Opzione 2 per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="3072e-142">Simple URL Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3072e-143"><strong>URL semplice</strong></span><span class="sxs-lookup"><span data-stu-id="3072e-143"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="3072e-144"><strong>Esempio</strong></span><span class="sxs-lookup"><span data-stu-id="3072e-144"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3072e-145">Soddisfare</span><span class="sxs-lookup"><span data-stu-id="3072e-145">Meet</span></span></p></td>
<td><p><span data-ttu-id="3072e-146">https://lync.contoso.com/Meethttps://lync.fabrikam.com/Meete così via (uno per ogni dominio SIP dell'organizzazione)</span><span class="sxs-lookup"><span data-stu-id="3072e-146">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3072e-147">Accesso esterno</span><span class="sxs-lookup"><span data-stu-id="3072e-147">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3072e-148">Amministratore</span><span class="sxs-lookup"><span data-stu-id="3072e-148">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a><span data-ttu-id="3072e-149">Opzione 3 per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="3072e-149">Simple URL Option 3</span></span>

<span data-ttu-id="3072e-p110">L'opzione 3 è più utile se si dispone di numerosi domini SIP e si desidera che dispongano di URL semplici separati, riducendo però al minimo i requisiti dei certificati e dei record DNS per questi URL semplici. In questo esempio è necessario un solo record A DNS per la risoluzione di lync.contoso.com nell'indirizzo IP di un pool di server Director o di un pool Front End.</span><span class="sxs-lookup"><span data-stu-id="3072e-p110">Option 3 is most useful if you have many SIP domains, and you want them to have separate simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs. In this example, you need only one DNS A record, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span>

### <a name="simple-url-option-3"></a><span data-ttu-id="3072e-152">Opzione 3 per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="3072e-152">Simple URL Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3072e-153"><strong>URL semplice</strong></span><span class="sxs-lookup"><span data-stu-id="3072e-153"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="3072e-154"><strong>Esempio</strong></span><span class="sxs-lookup"><span data-stu-id="3072e-154"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3072e-155">Soddisfare</span><span class="sxs-lookup"><span data-stu-id="3072e-155">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3072e-156">Accesso esterno</span><span class="sxs-lookup"><span data-stu-id="3072e-156">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3072e-157">Amministratore</span><span class="sxs-lookup"><span data-stu-id="3072e-157">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="3072e-158">Opzione di ripristino di emergenza per gli URL semplici</span><span class="sxs-lookup"><span data-stu-id="3072e-158">Disaster Recovery Option for Simple URLs</span></span>

<span data-ttu-id="3072e-159">Se si dispone di più siti che contengono pool Front end e il provider DNS supporta GeoDNS, è possibile configurare i record DNS per gli URL semplici che supportano il ripristino di emergenza, in modo che la funzionalità degli URL semplici prosegua anche se un intero pool Front-end viene premuto.</span><span class="sxs-lookup"><span data-stu-id="3072e-159">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="3072e-160">Questa funzionalità di ripristino di emergenza supporta gli URL semplici Meet e dial-in.</span><span class="sxs-lookup"><span data-stu-id="3072e-160">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="3072e-p112">Per eseguire questa configurazione, creare due indirizzi GeoDNS. Ogni indirizzo presenta due record DNS A o CNAME che si risolvono in due pool che vengono accoppiati per il ripristino di emergenza. Un indirizzo GeoDNS viene usato per l'accesso interno e si risolve nell'FQDN Web interno o nell'indirizzo IP del bilanciamento del carico per i due pool. L'altro indirizzo GeoDNS viene usato per l'accesso esterno e si risolve nell'FQDN Web esterno o nell'indirizzo IP del bilanciamento del carico per i due pool. Di seguito viene riportato un esempio dell'URL semplice Riunione, in cui vengono usati gli FQDN per i pool.</span><span class="sxs-lookup"><span data-stu-id="3072e-p112">To configure this, create two GeoDNS addresses. Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes. One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools. The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools. The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span>

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

<span data-ttu-id="3072e-166">Creare quindi i record CNAME che risolvono l'URL semplice riunione (ad esempio meet.contoso.com) nei due indirizzi GeoDNS.</span><span class="sxs-lookup"><span data-stu-id="3072e-166">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="3072e-167">Se la rete usa l'<EM>hairpin</EM> (ovvero il routing di tutto il traffico degli URL semplici attraverso il collegamento esterno, incluso il traffico proveniente dall'organizzazione), è sufficiente configurare l'indirizzo GeoDNS esterno e risolvere l'URL semplice riunione solo nell'indirizzo esterno specifico.</span><span class="sxs-lookup"><span data-stu-id="3072e-167">If your network uses <EM>hairpinning</EM> (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>



</div>

<span data-ttu-id="3072e-168">Quando si usa questo metodo, è possibile configurare ciascun indirizzo GeoDNS in modo che usi un metodo round robin per distribuire le richieste nei due pool oppure per effettuare la connessione principalmente a un pool (ad esempio il pool geograficamente più vicino) e usare l'altro pool solo in caso di errore di connettività.</span><span class="sxs-lookup"><span data-stu-id="3072e-168">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span>

<span data-ttu-id="3072e-169">È possibile specificare la stessa configurazione per l'URL semplice per accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="3072e-169">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="3072e-170">A tale scopo, creare record aggiuntivi come quelli nell'esempio precedente, sostituendo `dialin` `meet` nei record DNS.</span><span class="sxs-lookup"><span data-stu-id="3072e-170">To do so, create additional records like those in the previous example, substituting `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="3072e-171">Per l'URL semplice di amministrazione, usare una delle tre opzioni elencate precedentemente in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="3072e-171">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="3072e-172">Dopo avere completato la configurazione, è necessario usare un'applicazione di monitoraggio per impostare il monitoraggio HTTP per il controllo degli errori.</span><span class="sxs-lookup"><span data-stu-id="3072e-172">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="3072e-173">Per l'accesso esterno, monitorare per assicurarsi che HTTPS ottenere richieste di individuazione automatica per l'FQDN Web esterno o l'indirizzo IP del bilanciamento del carico per i due pool siano riusciti.</span><span class="sxs-lookup"><span data-stu-id="3072e-173">For external access, monitor to make sure that HTTPS GET autodiscovery requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="3072e-174">Ad esempio, le richieste seguenti non devono includere alcuna intestazione **ACCEPT** e devono restituire **200 OK**.</span><span class="sxs-lookup"><span data-stu-id="3072e-174">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="3072e-p115">Per l'accesso interno, è necessario monitorare la porta 5061 nell'FQDN Web interno o nell'indirizzo IP del bilanciamento del carico per i due pool. Se vengono rilevati errori di connettività, il VIP per i pool interessati deve chiudere le porte 80, 443 e 444.</span><span class="sxs-lookup"><span data-stu-id="3072e-p115">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools. If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 444.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

