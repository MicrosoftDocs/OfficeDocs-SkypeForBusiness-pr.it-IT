---
title: Supporto di Lync Server 2013 per la connettività di messaggistica istantanea pubblica
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c89cc911411095034385f7b8ebbe01edddcd20c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a><span data-ttu-id="c887c-102">Supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c887c-102">Support for public instant messenger connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c887c-103">_**Argomento Ultima modifica:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="c887c-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a><span data-ttu-id="c887c-104">Supporto per la connettività di messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="c887c-104">Support for Public Instant Messenger Connectivity</span></span>

<span data-ttu-id="c887c-105">Questo articolo fornisce informazioni sul supporto per la connettività di messaggistica istantanea pubblica (PIC).</span><span class="sxs-lookup"><span data-stu-id="c887c-105">This article provides information about support for Public IM Connectivity (PIC).</span></span> <span data-ttu-id="c887c-106">PIC è una funzionalità di Microsoft Lync che consente alle organizzazioni di consentire agli utenti di Lync di connettersi con utenti di determinati servizi di messaggistica istantanea pubblica tramite i client e le identità di Lync.</span><span class="sxs-lookup"><span data-stu-id="c887c-106">PIC is a feature of Microsoft Lync that allows organizations to enable their Lync users to connect with users of certain public instant messaging (IM) services through their Lync clients and identities.</span></span>

<span data-ttu-id="c887c-107">Gli utenti finali traggono vantaggio dall'essere in grado di connettersi con clienti, partner e fornitori in base alle proprie condizioni.</span><span class="sxs-lookup"><span data-stu-id="c887c-107">End-users benefit from being able to connect with customers, partners, and vendors on their terms.</span></span> <span data-ttu-id="c887c-108">Beneficia del supporto di un singolo client di comunicazioni in tempo reale mantenendo le funzionalità di controllo, conformità e archiviazione di Lync.</span><span class="sxs-lookup"><span data-stu-id="c887c-108">IT benefits from supporting a single real-time communications client while maintaining the control, compliance, and archiving features of Lync.</span></span> <span data-ttu-id="c887c-109">La connettività Lync-Skype, [disponibile pubblicamente in maggio 2013](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), si basa sull'eredità che Lync/Office Communications Server (OCS)/Live Communications Server (LCS) ha stabilito per la prima volta con pic per la connessione a MSN/Windows Live, AOL e Yahoo.</span><span class="sxs-lookup"><span data-stu-id="c887c-109">Lync-Skype connectivity, [publicly available in May 2013](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx), relies on the legacy that Lync/Office Communications Server (OCS)/Live Communications Server (LCS) first established with PIC in connecting to MSN/Windows Live, AOL, and Yahoo.</span></span><span data-ttu-id="c887c-110">Per altre informazioni sulla connettività Lync-Skype, vedere la [connettività Lync-Skype](http://office.microsoft.com/en-us/lync/lync-skype-connectivity-fx103789635.aspx).</span><span class="sxs-lookup"><span data-stu-id="c887c-110">  For more information on Lync-Skype connectivity, see the [Lync-Skype connectivity](http://office.microsoft.com/en-us/lync/lync-skype-connectivity-fx103789635.aspx).</span></span> <span data-ttu-id="c887c-111">La Federazione con Windows Live, AOL e Yahoo si trova su un percorso verso la fine della vita.</span><span class="sxs-lookup"><span data-stu-id="c887c-111">Federation with Windows Live, AOL, and Yahoo are each on a path towards end-of-life.</span></span><span data-ttu-id="c887c-112">Questa pagina documenta lo stato di ogni servizio.</span><span class="sxs-lookup"><span data-stu-id="c887c-112"> This page documents the status of each service.</span></span>

<span data-ttu-id="c887c-113">Per usare PIC, è necessario che i clienti attivino il servizio per ogni provider di servizi di messaggistica istantanea pubblica.</span><span class="sxs-lookup"><span data-stu-id="c887c-113">To use PIC, customers have been required to activate the service for each public IM service provider.</span></span> <span data-ttu-id="c887c-114">I requisiti e i dettagli su come eseguire questa operazione dipendono dal provider di servizi di messaggistica istantanea e dal programma di licenze sottostante del cliente.</span><span class="sxs-lookup"><span data-stu-id="c887c-114">The requirements and details for how to do this are dependent upon the IM service provider and the customer's underlying licensing program.</span></span>

<div>

## <a name="windows-live-messenger"></a><span data-ttu-id="c887c-115">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c887c-115">Windows Live Messenger</span></span>

<span data-ttu-id="c887c-116">Microsoft ha portato Windows Live Messenger e Skype insieme.</span><span class="sxs-lookup"><span data-stu-id="c887c-116">Microsoft brought Windows Live Messenger and Skype together.</span></span> <span data-ttu-id="c887c-117">In aprile 2013 gli utenti di Messenger venivano migrati in Skype upon Sign-in.</span><span class="sxs-lookup"><span data-stu-id="c887c-117">In April 2013, Messenger users were migrated to Skype upon sign-in.</span></span> <span data-ttu-id="c887c-118">I clienti di Lync che si affidano alla Federazione con Messenger continueranno a comunicare con i loro contatti di Messenger, anche dopo l'aggiornamento di questi contatti a Skype.</span><span class="sxs-lookup"><span data-stu-id="c887c-118">Lync customers who rely on federation with Messenger will continue to be able to communicate with their Messenger contacts, even after those contacts update to Skype.</span></span> <span data-ttu-id="c887c-119">Non c'è nulla che gli amministratori di Lync o gli utenti finali di Lync debbano eseguire per mantenere la continuità del servizio e la gestione di questa funzionalità in Lync rimanga la stessa per le comunicazioni con Messenger.</span><span class="sxs-lookup"><span data-stu-id="c887c-119">There is nothing that Lync administrators or Lync end-users need to do to maintain continuity of service, and management of this capability within Lync remains the same as it has been for communications with Messenger.</span></span> 

<span data-ttu-id="c887c-120">Quando gli utenti di Messenger entrano in Skype usando i loro account Microsoft (ad esempio le stesse credenziali usate per Messenger) tutti i loro contatti di Messenger, inclusi i contatti di Lync federati, li seguono in Skype.</span><span class="sxs-lookup"><span data-stu-id="c887c-120">When Messenger users sign into Skype using their Microsoft accounts (i.e., the same credentials used for Messenger) all of their Messenger contacts - including federated Lync contacts - follow them into Skype.</span></span> <span data-ttu-id="c887c-121">È disponibile la condivisione di presenza e la messaggistica istantanea tra Skype e Lync per questi contatti.</span><span class="sxs-lookup"><span data-stu-id="c887c-121">Presence sharing and instant messaging between Skype and Lync for these contacts is available.</span></span> 

<span data-ttu-id="c887c-122">Lync-Skype Connectivity-l'aggiunta di contatti, la condivisione della presenza, la messaggistica istantanea e le chiamate audio tra Lync e utenti Skype-è ora disponibile anche per tutti i clienti di Lync.</span><span class="sxs-lookup"><span data-stu-id="c887c-122">Lync-Skype connectivity - contact adding, presence sharing, instant messaging, and audio calling between Lync and Skype users - is also now available to all Lync customers.</span></span>

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a><span data-ttu-id="c887c-123">Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="c887c-123">Yahoo\!</span></span> <span data-ttu-id="c887c-124">e AOL Instant Messenger</span><span class="sxs-lookup"><span data-stu-id="c887c-124">and AOL Instant Messenger</span></span>

<span data-ttu-id="c887c-125">Federazione con Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="c887c-125">Federation with Yahoo\!</span></span> <span data-ttu-id="c887c-126">e AOL si trovano entrambi su un percorso verso la fine del ciclo di vita per i clienti di Lync (e Office Communications Server).</span><span class="sxs-lookup"><span data-stu-id="c887c-126">and AOL are both on a path toward end-of-life for customers of Lync (and Office Communications Server).</span></span> <span data-ttu-id="c887c-127">La capacità di Microsoft di prestare ognuno di questi servizi è stata condizionata al supporto di Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="c887c-127">Microsoft’s ability to provide each of these services has been contingent upon support from Yahoo\!</span></span> <span data-ttu-id="c887c-128">e AOL, e gli accordi sottostanti sono tortuosi.</span><span class="sxs-lookup"><span data-stu-id="c887c-128">and AOL, and the underlying agreements of these are winding down.</span></span> <span data-ttu-id="c887c-129">Sia per Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="c887c-129">For both Yahoo\!</span></span> <span data-ttu-id="c887c-130">e AOL, il servizio continuerà fino al 2014 giugno.</span><span class="sxs-lookup"><span data-stu-id="c887c-130">and AOL, service will continue through June 2014.</span></span>

  - <span data-ttu-id="c887c-131">**Yahoo** -Service continuerà attraverso il 2014 giugno e i clienti continueranno ad avere la licenza con la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL").</span><span class="sxs-lookup"><span data-stu-id="c887c-131">**Yahoo** - Service will continue through June 2014, and customers continue to need to be licensed with the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”).</span></span><span data-ttu-id="c887c-132">A partire dal 1 ° settembre 2012, il PIC USL, non è più disponibile per l'acquisto di contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="c887c-132">  As of September 1st, 2012, the PIC USL, is no longer available for purchase for new or renewing agreements.</span></span><span data-ttu-id="c887c-133">I clienti con licenze acquistate prima di questa data saranno in grado di continuare a eseguire la Federazione con Yahoo\!</span><span class="sxs-lookup"><span data-stu-id="c887c-133">  Customers with licenses purchased prior to this date will be able to continue to federate with Yahoo\!</span></span> <span data-ttu-id="c887c-134">fino alla data di chiusura del servizio precedente o alla scadenza della licenza.</span><span class="sxs-lookup"><span data-stu-id="c887c-134">until the earlier of the service shut down date or their license expiration.</span></span><span data-ttu-id="c887c-135">Leggere [l'annuncio](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) nel Blog del team Lync.</span><span class="sxs-lookup"><span data-stu-id="c887c-135"> Read [the announcement](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) on the Lync Team Blog.</span></span><span data-ttu-id="c887c-136">I clienti che hanno licenze PIC per accordi che si estendono oltre il 30 giugno 2014 riceveranno un credito in proporzione all'importo dei pagamenti che coprono il periodo di tempo successivo al 30 giugno 2014.</span><span class="sxs-lookup"><span data-stu-id="c887c-136"> Customers who have PIC licenses on agreements that extend past June 30, 2014 will receive a credit in proportion to the amount of the payments covering the time period following June 30, 2014.</span></span>

  - <span data-ttu-id="c887c-137">**AOL** -il 30 giugno 2014, il servizio connettività messaggistica istantanea di Lync ("pic") non sarà più disponibile.</span><span class="sxs-lookup"><span data-stu-id="c887c-137">**AOL** - On June 30, 2014, Lync's IM connectivity ("PIC") service will no longer be available.</span></span><span data-ttu-id="c887c-138">Per limitare la disgregazione del cliente al termine del servizio, è stato interrotto il provisioning di altri domini del cliente.</span><span class="sxs-lookup"><span data-stu-id="c887c-138"> In order to limit customer disruption when the service ends, we have discontinued the provisioning of additional customer domains.</span></span> <span data-ttu-id="c887c-139">Fino al 30 giugno 2014 i clienti non devono eseguire alcuna operazione per continuare a supportare le comunicazioni federate con AIM.</span><span class="sxs-lookup"><span data-stu-id="c887c-139">Until June 30, 2014, customers do not need to do anything to continue to support federated communications with AIM.</span></span> <span data-ttu-id="c887c-140">Oltre questa data (o per i clienti che desiderano eseguire il provisioning di altri domini nel frattempo), un servizio sostitutivo è disponibile direttamente da AOL.</span><span class="sxs-lookup"><span data-stu-id="c887c-140">Beyond this date (or for customers that would like to provision additional domains in the meantime), a substitute service is available directly from AOL.</span></span> <span data-ttu-id="c887c-141">Per altre informazioni sul nuovo servizio di AOL, vedere [creazione di una federazione diretta con AIM](http://aimenterprise.aol.com/pic.php)  (apre una nuova pagina in AOL.com).</span><span class="sxs-lookup"><span data-stu-id="c887c-141">For more information on AOL's new service, see [Establishing Direct Federation with AIM](http://aimenterprise.aol.com/pic.php)  (opens new page on AOL.com).</span></span>  

</div>

<div>

## <a name="public-im-provider-summary"></a><span data-ttu-id="c887c-142">Riepilogo del provider di messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="c887c-142">Public IM Provider Summary</span></span>

<span data-ttu-id="c887c-143">La tabella seguente contiene un riepilogo dei provider di servizi di messaggistica istantanea pubblici, le funzionalità federative con Lync e i requisiti di licenza.</span><span class="sxs-lookup"><span data-stu-id="c887c-143">The following table provides a summary of the Public IM service providers, federation capabilities with Lync, and licensing requirements.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c887c-144">Provider di servizi di messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="c887c-144">Public IM Service Provider</span></span></th>
<th><span data-ttu-id="c887c-145">Funzionalità federate</span><span class="sxs-lookup"><span data-stu-id="c887c-145">Federated Capabilities</span></span></th>
<th><span data-ttu-id="c887c-146">Requisiti per le licenze</span><span class="sxs-lookup"><span data-stu-id="c887c-146">Licensing Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c887c-147">Skype</span><span class="sxs-lookup"><span data-stu-id="c887c-147">Skype</span></span></p></td>
<td><p><span data-ttu-id="c887c-148">Messaggistica istantanea, presenza, audio</span><span class="sxs-lookup"><span data-stu-id="c887c-148">IM, Presence, Audio</span></span></p></td>
<td><p><span data-ttu-id="c887c-149">Licenze di accesso client di Lync Server, Lync Online piano 1/2/3</span><span class="sxs-lookup"><span data-stu-id="c887c-149">Lync Server Client Access Licenses, Lync Online Plan 1/2/3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887c-150">Windows Live Messenger</span><span class="sxs-lookup"><span data-stu-id="c887c-150">Windows Live Messenger</span></span></p></td>
<td><p><span data-ttu-id="c887c-151">Messaggistica istantanea, presenza, audio/video</span><span class="sxs-lookup"><span data-stu-id="c887c-151">IM, Presence, Audio/Video</span></span></p></td>
<td><p><span data-ttu-id="c887c-152">Licenze di accesso client di Lync Server (supportate purché WLM sia in commercio)</span><span class="sxs-lookup"><span data-stu-id="c887c-152">Lync Server Client Access Licenses (supported as long as WLM is in market)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887c-153">AOL</span><span class="sxs-lookup"><span data-stu-id="c887c-153">AOL</span></span></p></td>
<td><p><span data-ttu-id="c887c-154">Messaggistica istantanea, presenza</span><span class="sxs-lookup"><span data-stu-id="c887c-154">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="c887c-155">Licenze di accesso client di Lync Server; supportato tramite 2014 giugno per i clienti esistenti.</span><span class="sxs-lookup"><span data-stu-id="c887c-155">Lync Server Client Access Licenses; supported through June 2014 for existing customers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887c-156">Yahoo!</span><span class="sxs-lookup"><span data-stu-id="c887c-156">Yahoo!</span></span></p></td>
<td><p><span data-ttu-id="c887c-157">Messaggistica istantanea, presenza</span><span class="sxs-lookup"><span data-stu-id="c887c-157">IM, Presence</span></span></p></td>
<td><p><span data-ttu-id="c887c-158">È necessaria una licenza aggiuntiva per l'abbonamento a Microsoft Lync Public IM Connectivity ("PIC USL") oltre alle licenze di accesso client di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c887c-158">Requires additional Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) in addition to Lync Server Client Access Licences.</span></span> <span data-ttu-id="c887c-159">A partire dal listino prezzi di settembre 2012, il PIC USL non è più disponibile per l'acquisto.</span><span class="sxs-lookup"><span data-stu-id="c887c-159">As of the September 2012 Price List, the PIC USL is no longer available for purchase.</span></span> <span data-ttu-id="c887c-160">I clienti con licenze attive possono continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="c887c-160">Customers with active licenses are able to continue to federate with Yahoo!</span></span> <span data-ttu-id="c887c-161">Messenger fino alla data di chiusura del servizio il 30 giugno 2014.</span><span class="sxs-lookup"><span data-stu-id="c887c-161">Messenger until the service shut down date on June 30, 2014.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

