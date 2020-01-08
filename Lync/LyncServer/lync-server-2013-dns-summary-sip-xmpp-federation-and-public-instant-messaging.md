---
title: Riepilogo DNS-SIP, Federazione XMPP e messaggistica istantanea pubblica
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - SIP, XMPP federation, and public instant messaging
ms:assetid: 1ed24fb8-a849-44c0-a52e-7aef7527e644
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618369(v=OCS.15)
ms:contentKeyID: 49105656
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c22b38fdb9e936df8b3fd148022acdbd857cdcfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980740"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="8a336-102">Riepilogo DNS-SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a336-102">DNS summary - SIP, XMPP federation, and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a336-103">_**Argomento Ultima modifica:** 2017-03-09_</span><span class="sxs-lookup"><span data-stu-id="8a336-103">_**Topic Last Modified:** 2017-03-09_</span></span>

<span data-ttu-id="8a336-104">I record DNS (Domain Name System) necessari per la definizione di una federazione con Office Communications Server o i partner di Lync Server sono determinati dalla decisione di consentire l'individuazione automatica di DNS del dominio da parte di altri partner prospettici.</span><span class="sxs-lookup"><span data-stu-id="8a336-104">The Domain Name System (DNS) records that will be required for defining a federation with Office Communications Server or Lync Server partners is determined by your decision to either allow automatic DNS discovery of your domain by other perspective partners.</span></span> <span data-ttu-id="8a336-105">Se pubblichi il \_sipfederationtls. \_TCP.</span><span class="sxs-lookup"><span data-stu-id="8a336-105">If you publish the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="8a336-106">\* \<Nome\> di dominio SIP\* Record SRV, qualsiasi altro dominio federato SIP sarà in grado di "individuare" la Federazione.</span><span class="sxs-lookup"><span data-stu-id="8a336-106">*\<SIP domain name\>* SRV record, any other SIP federated domain will be able to “discover” your federation.</span></span> <span data-ttu-id="8a336-107">È possibile controllare quali domini federati possono comunicare con l'utente usando le impostazioni consente domini e domini bloccati nel pannello di controllo di Lync Server o impostando la configurazione dei domini consentiti o bloccati tramite Lync Server Management Shell e i cmdlet di PowerShell **Get**, **set**, **New**, **Remove-CsAllowedDomain** e **-CsBlockedDomain** .</span><span class="sxs-lookup"><span data-stu-id="8a336-107">You can control which federated domains can communicate with you by using the Allows domains and Blocked Domains settings in the Lync Server Control Panel, or by setting the allowed or blocked domains configuration using the Lync Server Management Shell and the **Get**, **Set**, **New**, **Remove-CsAllowedDomain** and **-CsBlockedDomain** PowerShell cmdlets.</span></span> <span data-ttu-id="8a336-108">Per altre informazioni su come configurare le impostazioni di tesi e l'uso dei cmdlet di PowerShell, vedere **argomenti correlati** alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="8a336-108">For additional information on how to configure theses settings and the use of the PowerShell cmdlets, see **Related Topics** at the end of this topic.</span></span>

<span data-ttu-id="8a336-109">La tabella di riepilogo DNS Records descrive le voci necessarie per una federazione aperta o individuabile.</span><span class="sxs-lookup"><span data-stu-id="8a336-109">The DNS records summary table depicts the required entries for an open, or discoverable, federation.</span></span> <span data-ttu-id="8a336-110">Se non si vuole implementare l'individuazione della \_Federazione, è possibile decidere di non configurare sipfederationtls. \_TCP.</span><span class="sxs-lookup"><span data-stu-id="8a336-110">If you do not want to implement Federation Discovery, You can decide to not configure the \_sipfederationtls.\_tcp.</span></span> <span data-ttu-id="8a336-111">Record del *nome\> di dominio SIP. \<*</span><span class="sxs-lookup"><span data-stu-id="8a336-111">*\<SIP domain name\>* record.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="8a336-112">Esistono scenari specifici in cui è necessario avere la _sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="8a336-112">There are specific scenarios in which you must have the _sipfederationtls._tcp.</span></span> <span data-ttu-id="8a336-113"><EM> &lt;Nome&gt; di dominio SIP</EM> Record SRV, ma non si vuole avere una Federazione individuabile.</span><span class="sxs-lookup"><span data-stu-id="8a336-113"><EM>&lt;SIP domain name&gt;</EM> SRV record, but you do not want to have a discoverable federation.</span></span> <span data-ttu-id="8a336-114">Una di queste istanze è la posizione in cui è stata distribuita la mobilità per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="8a336-114">One such instance is where you have deployed mobility for your users.</span></span> <span data-ttu-id="8a336-115">Il dispositivo di compensazione delle notifiche push (centro PNCH) è un tipo speciale di Federazione usato per i client di Microsoft Lync Mobile su Apple iPhone o iPad usando il client mobile Lync 2010 o Windows Phone usando i client mobili Lync 2010 mobile o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8a336-115">The mobility push notification clearinghouse (PNCH) is a special type of federation that is used for Microsoft Lync Mobile clients on Apple iPhone or iPad using the Lync 2010 Mobile client or Windows Phone using the Lync 2010 Mobile or Lync 2013 Mobile clients.</span></span> <span data-ttu-id="8a336-116">Il _sipfederationtls. _tcp.</span><span class="sxs-lookup"><span data-stu-id="8a336-116">The _sipfederationtls._tcp.</span></span> <span data-ttu-id="8a336-117"><EM> &lt;Nome&gt; di dominio SIP</EM> Il record SRV viene usato in caso di mobilità e notifica push.</span><span class="sxs-lookup"><span data-stu-id="8a336-117"><EM>&lt;SIP domain name&gt;</EM> SRV record is used in the case of mobility and push notification.</span></span> <span data-ttu-id="8a336-118">Per attenuare il problema e controllare la propria individuabilità, deselezionare l'opzione <STRONG>Abilita individuazione dominio partner</STRONG> per disattivare l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="8a336-118">To mitigate this issue and control your discoverability, clear the setting <STRONG>Enable partner domain discovery</STRONG> to turn off discovery.</span></span>



</div>

<span data-ttu-id="8a336-119">Per configurare il protocollo XMPP (Extensible Messaging and Presence Protocol) per la distribuzione, è possibile creare due record DNS (Domain Name System) in un server DNS esterno che risolverà i record nel servizio Edge di Access del server perimetrale o del pool di Edge.</span><span class="sxs-lookup"><span data-stu-id="8a336-119">To configure extensible messaging and presence protocol (XMPP) for your deployment, you create two domain name system (DNS) records in an external DNS server that will resolve the records to the Access Edge service of your Edge Server or Edge pool.</span></span>

<span data-ttu-id="8a336-120">Quando si configura Domain Name System (DNS) per la connettività di messaggistica istantanea pubblica, si verificherà che la configurazione che supporta gli utenti esterni supporta la connettività di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="8a336-120">When you configure domain name system (DNS) for public instant messaging connectivity, you will find that the configuration that supports external users will support public IM connectivity.</span></span> <span data-ttu-id="8a336-121">Se è già stato configurato il server perimetrale o il pool di Edge, è necessario disporre dei record DNS necessari per supportare la connettività di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="8a336-121">If you have already configured your Edge Server or Edge pool, you should have the DNS records necessary to support public IM connectivity.</span></span>

<div>

## <a name="dns-summary---sip-federation-including-public-instant-messaging-connectivity"></a><span data-ttu-id="8a336-122">Riepilogo DNS-federazione SIP inclusa la connettività di messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="8a336-122">DNS Summary - SIP Federation including Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a336-123">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="8a336-123">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="8a336-124">FQDN</span><span class="sxs-lookup"><span data-stu-id="8a336-124">FQDN</span></span></th>
<th><span data-ttu-id="8a336-125">Indirizzo IP/record host FQDN</span><span class="sxs-lookup"><span data-stu-id="8a336-125">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="8a336-126">Mapping a/commenti</span><span class="sxs-lookup"><span data-stu-id="8a336-126">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a336-127">DNS esterno/SRV/5061</span><span class="sxs-lookup"><span data-stu-id="8a336-127">External DNS/SRV/5061</span></span></p></td>
<td><p><span data-ttu-id="8a336-128">_sipfederationtls. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="8a336-128">_sipfederationtls._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8a336-129">sip.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8a336-129">sip.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8a336-130">Interfaccia esterna di Access Edge service necessaria per l'individuazione automatica del DNS della Federazione ad altri potenziali partner federativi ed è nota come "domini SIP consentiti" (chiamata federazione avanzata nelle versioni precedenti). Ripetere la procedura necessaria per tutti i domini SIP con gli utenti abilitati a Lync</span><span class="sxs-lookup"><span data-stu-id="8a336-130">Access Edge service external interface Required for automatic DNS discovery of your federation to other potential federation partners, and is known as “Allowed SIP Domains” (called enhanced federation in previous releases).Repeat as necessary for all SIP domains with Lync enabled users</span></span></p>



> [!IMPORTANT]
> <span data-ttu-id="8a336-131">Questo record SRV è necessario per la mobilità e la camera di compensazione delle notifiche push.</span><span class="sxs-lookup"><span data-stu-id="8a336-131">This SRV record is required for mobility and the push notification clearing house.</span></span> <span data-ttu-id="8a336-132">Nei casi in cui è presente più di un dominio SIP, creare e pubblicare un record SRV per ogni dominio che avrà client di Lync mobile.</span><span class="sxs-lookup"><span data-stu-id="8a336-132">In cases where there is more than one SIP domain, create and publish an SRV record for each domain that will have Lync Mobile clients.</span></span> <span data-ttu-id="8a336-133">Il servizio di notifica push e il servizio di notifica push Apple potrebbero non funzionare come previsto se non è presente un record SRV esplicito per ogni dominio SIP supportato dalla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8a336-133">The Push Notification Service and Apple Push Notification service may not operate as expected if there is not an explicit SRV record for each SIP domain that the deployment supports.</span></span>

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary---extensible-messaging-and-presence-protocol-xmpp"></a><span data-ttu-id="8a336-134">Riepilogo DNS-protocollo XMPP (Extensible Messaging and Presence Protocol)</span><span class="sxs-lookup"><span data-stu-id="8a336-134">DNS Summary - Extensible Messaging and Presence Protocol (XMPP)</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8a336-135">Posizione/tipo/porta</span><span class="sxs-lookup"><span data-stu-id="8a336-135">Location/TYPE/Port</span></span></th>
<th><span data-ttu-id="8a336-136">FQDN</span><span class="sxs-lookup"><span data-stu-id="8a336-136">FQDN</span></span></th>
<th><span data-ttu-id="8a336-137">Indirizzo IP/record host FQDN</span><span class="sxs-lookup"><span data-stu-id="8a336-137">IP address/FQDN host record</span></span></th>
<th><span data-ttu-id="8a336-138">Mapping a/commenti</span><span class="sxs-lookup"><span data-stu-id="8a336-138">Maps to/Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8a336-139">DNS esterno/SRV/5269</span><span class="sxs-lookup"><span data-stu-id="8a336-139">External DNS/SRV/5269</span></span></p></td>
<td><p><span data-ttu-id="8a336-140">_xmpp-server. _tcp. contoso. com</span><span class="sxs-lookup"><span data-stu-id="8a336-140">_xmpp-server._tcp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8a336-141">xmpp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8a336-141">xmpp.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="8a336-142">Interfaccia esterna proxy XMPP nel pool di servizi o Edge di Access. Ripetere l'impostazione necessaria per tutti i domini SIP interni con gli utenti abilitati a Lync in cui è consentito il contatto con i contatti XMPP tramite la configurazione dei criteri di accesso esterno tramite un criterio globale, il criterio del sito in cui si trova l'utente o i criteri degli utenti applicati alla Utenti abilitati per Lync.</span><span class="sxs-lookup"><span data-stu-id="8a336-142">XMPP proxy external interface on the Access Edge service or Edge pool.Repeat as necessary for all internal SIP domains with Lync enabled users where contact with XMPP contacts is allowed through the configuration of the External Access Policy through a global policy, site policy where the user is located, or user policy applied to the Lync-enabled user.</span></span> <span data-ttu-id="8a336-143">Un dominio XMPP consentito deve essere configurato anche nei criteri dei partner federati XMPP.</span><span class="sxs-lookup"><span data-stu-id="8a336-143">An allowed XMPP domain must also be configured in the XMPP Federated Partners policy.</span></span> <span data-ttu-id="8a336-144">Vedere gli argomenti in <strong>vedere anche</strong> per ulteriori dettagli</span><span class="sxs-lookup"><span data-stu-id="8a336-144">See topics in <strong>See Also</strong> for additional details</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8a336-145">DNS esterno/A</span><span class="sxs-lookup"><span data-stu-id="8a336-145">External DNS/A</span></span></p></td>
<td><p><span data-ttu-id="8a336-146">xmpp.contoso.com (ad esempio)</span><span class="sxs-lookup"><span data-stu-id="8a336-146">xmpp.contoso.com (for example)</span></span></p></td>
<td><p><span data-ttu-id="8a336-147">Indirizzo IP del servizio Access Edge nell'Edge Server o nel pool di Edge che ospita il proxy XMPP</span><span class="sxs-lookup"><span data-stu-id="8a336-147">IP address of Access Edge service on your Edge Server or Edge pool hosting XMPP proxy</span></span></p></td>
<td><p><span data-ttu-id="8a336-148">Punta al servizio di Access Edge o al pool di Edge che ospita il servizio proxy XMPP.</span><span class="sxs-lookup"><span data-stu-id="8a336-148">Points to the Access Edge service or Edge pool that hosts the XMPP proxy service.</span></span> <span data-ttu-id="8a336-149">In genere, il record SRV creato punterà al record host (A o AAAA)</span><span class="sxs-lookup"><span data-stu-id="8a336-149">Typically, the SRV record that you create will point to this host (A or AAAA) record</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8a336-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a336-150">See Also</span></span>


[<span data-ttu-id="8a336-151">Configurazione della federazione di XMPP in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a336-151">Setting up XMPP federation in Lync Server 2013</span></span>](lync-server-2013-setting-up-xmpp-federation.md)  
[<span data-ttu-id="8a336-152">Configurazione delle notifiche push in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a336-152">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
[<span data-ttu-id="8a336-153">Abilitare o disabilitare l'individuazione dei partner della federazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a336-153">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)  


[<span data-ttu-id="8a336-154">Scenari per l'accesso degli utenti esterni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a336-154">Scenarios for external user access in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-external-user-access.md)  
[<span data-ttu-id="8a336-155">Determinare i requisiti di DNS per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a336-155">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  


[<span data-ttu-id="8a336-156">Gestire i domini federati SIP per l'organizzazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a336-156">Manage SIP federated domains for your organization in Lync Server 2013</span></span>](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

