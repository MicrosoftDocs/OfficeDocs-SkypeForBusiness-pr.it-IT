---
title: 'Lync Server 2013: Pianificazione degli URL semplici'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17dbfce9f699f31e09bb66d6d596e0a3cbf0ba96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="06487-102">Pianificazione degli URL semplici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06487-102">Planning for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06487-103">_**Argomento Ultima modifica:** 2015-12-11_</span><span class="sxs-lookup"><span data-stu-id="06487-103">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="06487-104">Gli URL semplici semplificano la partecipazione alle riunioni per gli utenti e rendono più semplice l'accesso agli strumenti di amministrazione di Lync Server per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="06487-104">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="06487-105">Lync Server supporta tre semplici URL:</span><span class="sxs-lookup"><span data-stu-id="06487-105">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="06487-106">L' **incontro** viene usato come URL di base per tutte le conferenze nel sito o nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="06487-106">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="06487-107">Un esempio di URL semplice Meet è https://meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="06487-107">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="06487-108">Un URL per una determinata riunione può essere https://meet.contoso.com/ *nomeutente*/7322994.</span><span class="sxs-lookup"><span data-stu-id="06487-108">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="06487-109">Con l'URL semplice Meet, i collegamenti alle riunioni di partecipazione sono facili da comprendere e facili da comunicare e distribuire.</span><span class="sxs-lookup"><span data-stu-id="06487-109">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="06487-110">L'accesso esterno consente di accedere alla pagina Web delle impostazioni dei servizi di conferenza telefonica con **chiamata in ingresso** .</span><span class="sxs-lookup"><span data-stu-id="06487-110">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="06487-111">In questa pagina vengono visualizzati i numeri di accesso esterno per conferenze con le lingue disponibili, le informazioni sulla conferenza assegnate, ovvero per le riunioni che non devono essere pianificate, e i controlli DTMF in conferenza e supportano la gestione del numero di identificazione personale ( PIN) e informazioni di conferenza assegnate.</span><span class="sxs-lookup"><span data-stu-id="06487-111">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="06487-112">L'URL semplice per la chiamata in ingresso è incluso in tutti gli inviti alle riunioni, in modo che gli utenti che vogliono connettersi alla riunione possano accedere al numero di telefono e alle informazioni PIN necessarie.</span><span class="sxs-lookup"><span data-stu-id="06487-112">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="06487-113">Un esempio dell'URL semplice in accesso esterno è https://dialin.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="06487-113">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="06487-114">L' **amministratore** consente l'accesso rapido al pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06487-114">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="06487-115">Da qualsiasi computer all'interno del firewall dell'organizzazione, un amministratore può aprire il pannello di controllo di Lync Server digitando l'URL semplice amministratore in un browser.</span><span class="sxs-lookup"><span data-stu-id="06487-115">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="06487-116">L'URL semplice amministratore è interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="06487-116">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="06487-117">Un esempio dell'URL semplice di amministrazione èhttps://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="06487-117">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="06487-118">Ambito URL semplice</span><span class="sxs-lookup"><span data-stu-id="06487-118">Simple URL Scope</span></span>

<span data-ttu-id="06487-119">Puoi configurare gli URL semplici per avere un ambito globale oppure puoi specificare URL semplici diversi per ogni sito centrale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="06487-119">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="06487-120">Se sono specificati sia un URL semplice dell'ambito globale che un URL semplice per l'ambito del sito, l'URL semplice dell'ambito del sito ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="06487-120">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="06487-121">Nella maggior parte dei casi è consigliabile impostare URL semplici solo a livello globale, in modo che l'URL di riunione semplice dell'utente non venga modificato se si passa da un sito a un altro.</span><span class="sxs-lookup"><span data-stu-id="06487-121">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another.</span></span> <span data-ttu-id="06487-122">L'eccezione è costituita dalle organizzazioni che devono usare numeri di telefono diversi per gli utenti con accesso esterno in siti diversi.</span><span class="sxs-lookup"><span data-stu-id="06487-122">The exception would be organizations that need to use different telephone numbers for dial-in users at different sites.</span></span> <span data-ttu-id="06487-123">Tieni presente che se imposti un semplice URL (ad esempio l'URL semplice in accesso esterno) in un sito per essere un URL semplice a livello di sito, devi anche impostare gli altri URL semplici di tale sito come a livello di sito.</span><span class="sxs-lookup"><span data-stu-id="06487-123">Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="06487-124">Se si sceglie di usare URL semplici con ambito sito, gli utenti non saranno in grado di spostarsi tra i pool Front-end in siti diversi senza che gli utenti riprogrammano tutte le riunioni pianificate, poiché gli URL semplici della riunione sono diversi tra i siti.</span><span class="sxs-lookup"><span data-stu-id="06487-124">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="06487-125">Questo include scenari di failover in cui i pool nelle relazioni di backup si trovano in siti distinti.</span><span class="sxs-lookup"><span data-stu-id="06487-125">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="06487-126">Quando è necessario eseguire il failover tra i siti in cui vengono distribuiti URL semplici con ambito sito, gli utenti non potranno partecipare alle riunioni per l'ambito dell'URL.</span><span class="sxs-lookup"><span data-stu-id="06487-126">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="06487-127">Per altre informazioni, selezionare <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="06487-127">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="06487-128">Puoi impostare URL semplici globali in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="06487-128">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="06487-129">Per impostare un URL semplice a livello di sito, è necessario utilizzare il cmdlet Set-CsSimpleURLConfiguration.</span><span class="sxs-lookup"><span data-stu-id="06487-129">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="06487-130">Denominazione degli URL semplici</span><span class="sxs-lookup"><span data-stu-id="06487-130">Naming Your Simple URLs</span></span>

<span data-ttu-id="06487-131">Sono disponibili tre opzioni consigliate per la denominazione degli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="06487-131">There are three recommended options for naming your simple URLs.</span></span> <span data-ttu-id="06487-132">Quale opzione si sceglie ha implicazioni per configurare i record DNS e i certificati che supportano gli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="06487-132">Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs.</span></span> <span data-ttu-id="06487-133">In ogni opzione è necessario configurare un URL semplice di riunione per ogni dominio SIP dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="06487-133">In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="06487-134">È sempre necessario un solo URL semplice nell'intera organizzazione per l'accesso esterno e uno per l'amministratore, indipendentemente dal numero di domini SIP.</span><span class="sxs-lookup"><span data-stu-id="06487-134">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="06487-135">Per informazioni dettagliate sui record e i certificati DNS necessari, vedere [requisiti DNS per gli URL semplici in Lync server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) e i [requisiti dei certificati per i server interni in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="06487-135">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="06487-136">Nell'opzione 1 si crea un nuovo nome di dominio SIP per ogni URL semplice.</span><span class="sxs-lookup"><span data-stu-id="06487-136">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="06487-137">Se si usa questa opzione, è necessario un record DNS distinto per ogni URL semplice e ogni URL semplice Meet deve essere denominato nei certificati.</span><span class="sxs-lookup"><span data-stu-id="06487-137">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="06487-138">Opzione di denominazione semplice URL 1</span><span class="sxs-lookup"><span data-stu-id="06487-138">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06487-139"><strong>URL semplice</strong></span><span class="sxs-lookup"><span data-stu-id="06487-139"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="06487-140"><strong>Esempio</strong></span><span class="sxs-lookup"><span data-stu-id="06487-140"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06487-141">Soddisfano</span><span class="sxs-lookup"><span data-stu-id="06487-141">Meet</span></span></p></td>
<td><p><span data-ttu-id="06487-142">https://meet.contoso.com, https://meet.fabrikam.come così via (uno per ogni dominio SIP nell'organizzazione)</span><span class="sxs-lookup"><span data-stu-id="06487-142">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06487-143">Accesso esterno</span><span class="sxs-lookup"><span data-stu-id="06487-143">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06487-144">Admin</span><span class="sxs-lookup"><span data-stu-id="06487-144">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="06487-145">Con l'opzione 2, gli URL semplici si basano sul nome di dominio lync.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="06487-145">With Option 2, simple URLs are based on the domain name lync.contoso.com.</span></span> <span data-ttu-id="06487-146">Di conseguenza, è necessario un solo record DNS che consenta A tutti e tre i tipi di URL semplici.</span><span class="sxs-lookup"><span data-stu-id="06487-146">Therefore, you need only one DNS A record which enables all three types of simple URLs.</span></span> <span data-ttu-id="06487-147">Questo record DNS fa riferimento A lync.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="06487-147">This DNS A record references lync.contoso.com.</span></span> <span data-ttu-id="06487-148">È inoltre necessario separare i record DNS per altri domini SIP nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="06487-148">Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="06487-149">Opzione di denominazione semplice URL 2</span><span class="sxs-lookup"><span data-stu-id="06487-149">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06487-150"><strong>URL semplice</strong></span><span class="sxs-lookup"><span data-stu-id="06487-150"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="06487-151"><strong>Esempio</strong></span><span class="sxs-lookup"><span data-stu-id="06487-151"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06487-152">Soddisfano</span><span class="sxs-lookup"><span data-stu-id="06487-152">Meet</span></span></p></td>
<td><p><span data-ttu-id="06487-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meete così via (uno per ogni dominio SIP nell'organizzazione)</span><span class="sxs-lookup"><span data-stu-id="06487-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06487-154">Accesso esterno</span><span class="sxs-lookup"><span data-stu-id="06487-154">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06487-155">Admin</span><span class="sxs-lookup"><span data-stu-id="06487-155">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="06487-156">L'opzione 3 è molto utile se si hanno molti domini SIP e si vuole che dispongano di URL semplici per riunioni separate, ma che si vogliano ridurre al minimo i requisiti di record e certificati DNS per questi URL semplici.</span><span class="sxs-lookup"><span data-stu-id="06487-156">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="06487-157">Opzione di denominazione URL semplice 3</span><span class="sxs-lookup"><span data-stu-id="06487-157">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06487-158"><strong>URL semplice</strong></span><span class="sxs-lookup"><span data-stu-id="06487-158"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="06487-159"><strong>Esempio</strong></span><span class="sxs-lookup"><span data-stu-id="06487-159"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06487-160">Soddisfano</span><span class="sxs-lookup"><span data-stu-id="06487-160">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06487-161">Accesso esterno</span><span class="sxs-lookup"><span data-stu-id="06487-161">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06487-162">Admin</span><span class="sxs-lookup"><span data-stu-id="06487-162">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="06487-163">Regole di denominazione e convalida URL semplici</span><span class="sxs-lookup"><span data-stu-id="06487-163">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="06487-164">Generatore di topologie e i cmdlet di Lync Server Management Shell applicano diverse regole di convalida per gli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="06487-164">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="06487-165">È necessario impostare URL semplici per le riunioni e la chiamata, ma l'impostazione di una per l'amministratore è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="06487-165">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="06487-166">Ogni dominio SIP deve avere un URL semplice Meet distinto, ma è necessario un solo URL semplice dialin e un URL semplice per l'amministratore per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="06487-166">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="06487-167">Ogni URL semplice nell'organizzazione deve avere un nome univoco e non può essere un prefisso di un altro URL semplice (ad esempio, non è stato possibile impostare lync.contoso.com/Meet come URL semplice di riunione e lync.contoso.com/Meet/Dialin come URL semplice di accesso esterno).</span><span class="sxs-lookup"><span data-stu-id="06487-167">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="06487-168">I nomi di URL semplici non possono contenere il nome di dominio completo di uno dei pool o qualsiasi informazione sulla https://FQDN:88/meet porta, ad esempio non è consentita.</span><span class="sxs-lookup"><span data-stu-id="06487-168">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="06487-169">Tutti gli URL semplici devono iniziare con il prefisso https://.</span><span class="sxs-lookup"><span data-stu-id="06487-169">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="06487-170">Gli URL semplici possono contenere solo caratteri alfanumerici, ovvero a-z, A-Z, 0-9 e il punto (.).</span><span class="sxs-lookup"><span data-stu-id="06487-170">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.).</span></span> <span data-ttu-id="06487-171">Se si usano altri caratteri, gli URL semplici potrebbero non funzionare come previsto.</span><span class="sxs-lookup"><span data-stu-id="06487-171">If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="06487-172">Modifica di URL semplici dopo la distribuzione</span><span class="sxs-lookup"><span data-stu-id="06487-172">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="06487-173">Se si modifica un URL semplice dopo la distribuzione iniziale, è necessario essere consapevoli del modo in cui la modifica influisce sui record DNS e sui certificati per gli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="06487-173">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="06487-174">Se la base di un URL semplice cambia, è necessario modificare anche i record DNS e i certificati.</span><span class="sxs-lookup"><span data-stu-id="06487-174">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="06487-175">Ad esempio, passando da https://lync.contoso.com/Meet per https://meet.contoso.com cambiare l'URL di base da Lync.contoso.com a meet.contoso.com, è necessario modificare i record DNS e i certificati per fare riferimento a meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="06487-175">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="06487-176">Se è stato modificato l'URL https://lync.contoso.com/Meet semplice https://lync.contoso.com/Meetings, l'url di base di Lync.contoso.com rimane invariato, quindi non sono necessarie modifiche DNS o di certificato.</span><span class="sxs-lookup"><span data-stu-id="06487-176">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="06487-177">Ogni volta che si modifica un nome di URL semplice, è necessario eseguire **Enable-CsComputer** su ogni Director e front end server per registrare la modifica.</span><span class="sxs-lookup"><span data-stu-id="06487-177">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="06487-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06487-178">See Also</span></span>


[<span data-ttu-id="06487-179">Requisiti DNS per gli URL semplici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06487-179">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

