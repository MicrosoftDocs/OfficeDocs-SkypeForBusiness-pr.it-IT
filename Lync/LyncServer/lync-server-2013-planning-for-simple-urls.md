---
title: 'Lync Server 2013: pianificazione per gli URL semplici'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for simple URLs
ms:assetid: 20e4f4b6-b7ff-4297-b00d-d1211ee800ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398287(v=OCS.15)
ms:contentKeyID: 48183610
ms.date: 12/12/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85b01956d901d5c4060dc1cf14f9991fdfce261c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="3b927-102">Pianificazione degli URL semplici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b927-102">Planning for simple URLs in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b927-103">_**Ultimo argomento modificato:** 2015-12-11_</span><span class="sxs-lookup"><span data-stu-id="3b927-103">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="3b927-104">Gli URL semplici agevolano la partecipazione alle riunioni per gli utenti e semplificano gli strumenti di amministrazione di Lync Server per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="3b927-104">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="3b927-105">Lync Server supporta tre URL semplici:</span><span class="sxs-lookup"><span data-stu-id="3b927-105">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="3b927-106">L'URL **riunione** (meet) viene utilizzato come URL di base per tutte le conferenze nel sito o nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3b927-106">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="3b927-107">Un esempio di URL semplice Meet è https://meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3b927-107">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="3b927-108">Un URL per una riunione specifica può essere https://meet.contoso.com/ *nomeutente*/7322994.</span><span class="sxs-lookup"><span data-stu-id="3b927-108">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="3b927-109">Con l'URL semplice riunione, i collegamenti per partecipare alle riunioni sono semplici da capire, da comunicare e da distribuire.</span><span class="sxs-lookup"><span data-stu-id="3b927-109">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="3b927-110">L'URL **per accesso esterno** (dialin) consente di accedere alla pagina Web Impostazioni conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="3b927-110">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="3b927-111">In questa pagina vengono visualizzati i numeri di accesso esterno alle conferenze con le lingue disponibili, le informazioni sulle conferenze assegnate, ovvero per le riunioni che non devono essere pianificate, e i controlli DTMF in-Conference e che supportano la gestione del numero di identificazione personale ( PIN) e informazioni per le conferenze assegnate.</span><span class="sxs-lookup"><span data-stu-id="3b927-111">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="3b927-112">L'URL semplice per accesso esterno è incluso in tutti gli inviti a riunioni, in modo che gli utenti che desiderano eseguire l'accesso esterno alla riunione dispongano delle informazioni necessarie sul numero di telefono e sul PIN.</span><span class="sxs-lookup"><span data-stu-id="3b927-112">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="3b927-113">Un esempio di URL semplice in accesso esterno è https://dialin.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3b927-113">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="3b927-114">L' **amministratore** consente di accedere rapidamente al pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3b927-114">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="3b927-115">Da qualsiasi computer all'interno dei firewall dell'organizzazione, un amministratore può aprire il pannello di controllo di Lync Server digitando l'URL semplice di amministrazione in un browser.</span><span class="sxs-lookup"><span data-stu-id="3b927-115">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="3b927-116">L'URL semplice di amministrazione è interno all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3b927-116">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="3b927-117">Un esempio di URL semplice di amministrazione èhttps://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="3b927-117">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="3b927-118">Ambito degli URL semplici</span><span class="sxs-lookup"><span data-stu-id="3b927-118">Simple URL Scope</span></span>

<span data-ttu-id="3b927-119">È possibile configurare gli URL semplici per un ambito globale oppure specificare URL semplici diversi per ogni sito centrale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3b927-119">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="3b927-120">Se sono specificati sia un URL semplice dell'ambito globale che un URL semplice dell'ambito del sito, l'URL semplice dell'ambito del sito ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="3b927-120">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="3b927-p105">Nella maggior parte dei casi, è consigliabile impostare gli URL semplici solo a livello globale, in modo che l'URL semplice riunione di un utente non cambi con lo spostamento da un sito a un altro. L'eccezione è rappresentata da organizzazioni che devono utilizzare numeri di telefono diversi per gli utenti connessi tramite chiamata in ingresso in siti diversi. Si noti che se si imposta in un sito un URL semplice a livello di sito, ad esempio per l'accesso esterno, sarà necessario impostare a livello di sito anche gli altri URL semplici del sito.</span><span class="sxs-lookup"><span data-stu-id="3b927-p105">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another. The exception would be organizations that need to use different telephone numbers for dial-in users at different sites. Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3b927-124">Se si sceglie di utilizzare gli URL semplici con ambito sito, gli utenti non saranno in grado di spostarsi tra i pool Front-end in siti diversi senza che gli utenti ripianificano tutte le riunioni pianificate, in quanto gli URL semplici della riunione sono diversi tra i siti.</span><span class="sxs-lookup"><span data-stu-id="3b927-124">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="3b927-125">Sono inclusi gli scenari di failover nei quali i pool nelle relazioni di backup si trovano in siti separati.</span><span class="sxs-lookup"><span data-stu-id="3b927-125">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="3b927-126">Quando è necessario eseguire il failover tra i siti in cui vengono distribuiti gli URL semplici con ambito del sito, gli utenti non saranno in grado di partecipare alle riunioni a causa dell'ambito per l'URL.</span><span class="sxs-lookup"><span data-stu-id="3b927-126">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="3b927-127">Per ulteriori informazioni, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="3b927-127">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="3b927-128">È possibile impostare gli URL semplici globali in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="3b927-128">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="3b927-129">Per impostare un URL semplice a livello di sito, è necessario utilizzare il cmdlet Set-CsSimpleURLConfiguration.</span><span class="sxs-lookup"><span data-stu-id="3b927-129">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="3b927-130">Denominazione degli URL semplici</span><span class="sxs-lookup"><span data-stu-id="3b927-130">Naming Your Simple URLs</span></span>

<span data-ttu-id="3b927-p108">Sono disponibili tre opzioni consigliate per denominare gli URL semplici. L'opzione scelta determina il modo in cui vengono configurati i certificati e i record A DNS che supportano gli URL semplici. In ogni opzione è necessario configurare un URL semplice riunione per ogni dominio SIP dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3b927-p108">There are three recommended options for naming your simple URLs. Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs. In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="3b927-134">Sono sufficienti sempre nell'intera organizzazione un solo URL semplice per accesso esterno e uno di amministrazione, indipendentemente dal numero di domini SIP presenti.</span><span class="sxs-lookup"><span data-stu-id="3b927-134">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="3b927-135">Per informazioni dettagliate sui record e i certificati DNS necessari, vedere [DNS requirements for Simple URLs in Lync server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) e [Certificate Requirements for Internal Servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="3b927-135">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="3b927-136">Nell'opzione 1 viene creato un nuovo nome di dominio SIP per ogni URL semplice.</span><span class="sxs-lookup"><span data-stu-id="3b927-136">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="3b927-137">Se si utilizza questa opzione, è necessario un record A DNS separato per ogni URL semplice e ogni URL semplice riunione deve essere denominato nei certificati.</span><span class="sxs-lookup"><span data-stu-id="3b927-137">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="3b927-138">Opzione 1 di denominazione degli URL semplici</span><span class="sxs-lookup"><span data-stu-id="3b927-138">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b927-139"><strong>URL semplice</strong></span><span class="sxs-lookup"><span data-stu-id="3b927-139"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="3b927-140"><strong>Esempio</strong></span><span class="sxs-lookup"><span data-stu-id="3b927-140"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b927-141">Soddisfare</span><span class="sxs-lookup"><span data-stu-id="3b927-141">Meet</span></span></p></td>
<td><p><span data-ttu-id="3b927-142">https://meet.contoso.comhttps://meet.fabrikam.come così via (uno per ogni dominio SIP dell'organizzazione)</span><span class="sxs-lookup"><span data-stu-id="3b927-142">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b927-143">Accesso esterno</span><span class="sxs-lookup"><span data-stu-id="3b927-143">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b927-144">Amministratore</span><span class="sxs-lookup"><span data-stu-id="3b927-144">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3b927-p109">Con l'opzione 2, gli URL semplici sono basati sul nome di dominio lync.contoso.com. È necessario pertanto un solo record A DNS che consenta tutti e tre i tipi di URL semplici. Questo record A DNS fa riferimento a lync.contoso.com. Sono sempre necessari però record A DNS separati per altri domini SIP dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3b927-p109">With Option 2, simple URLs are based on the domain name lync.contoso.com. Therefore, you need only one DNS A record which enables all three types of simple URLs. This DNS A record references lync.contoso.com. Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="3b927-149">Opzione 2 di denominazione degli URL semplici</span><span class="sxs-lookup"><span data-stu-id="3b927-149">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b927-150"><strong>URL semplice</strong></span><span class="sxs-lookup"><span data-stu-id="3b927-150"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="3b927-151"><strong>Esempio</strong></span><span class="sxs-lookup"><span data-stu-id="3b927-151"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b927-152">Soddisfare</span><span class="sxs-lookup"><span data-stu-id="3b927-152">Meet</span></span></p></td>
<td><p><span data-ttu-id="3b927-153">https://lync.contoso.com/Meethttps://lync.fabrikam.com/Meete così via (uno per ogni dominio SIP dell'organizzazione)</span><span class="sxs-lookup"><span data-stu-id="3b927-153">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b927-154">Accesso esterno</span><span class="sxs-lookup"><span data-stu-id="3b927-154">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b927-155">Amministratore</span><span class="sxs-lookup"><span data-stu-id="3b927-155">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3b927-156">L'opzione 3 è più utile se si dispone di numerosi domini SIP e si desidera che dispongano di URL semplici riunione separati, riducendo però al minimo i requisiti dei certificati e dei record DNS per questi URL semplici.</span><span class="sxs-lookup"><span data-stu-id="3b927-156">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="3b927-157">Opzione 3 di denominazione degli URL semplici</span><span class="sxs-lookup"><span data-stu-id="3b927-157">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b927-158"><strong>URL semplice</strong></span><span class="sxs-lookup"><span data-stu-id="3b927-158"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="3b927-159"><strong>Esempio</strong></span><span class="sxs-lookup"><span data-stu-id="3b927-159"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b927-160">Soddisfare</span><span class="sxs-lookup"><span data-stu-id="3b927-160">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b927-161">Accesso esterno</span><span class="sxs-lookup"><span data-stu-id="3b927-161">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b927-162">Amministratore</span><span class="sxs-lookup"><span data-stu-id="3b927-162">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="3b927-163">Regole di denominazione e convalida degli URL semplici</span><span class="sxs-lookup"><span data-stu-id="3b927-163">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="3b927-164">Il generatore di topologie e i cmdlet di Lync Server Management Shell applicano diverse regole di convalida per gli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="3b927-164">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="3b927-165">È obbligatorio impostare URL semplici riunione e per accesso esterno, mentre l'impostazione dell'URL semplice di amministrazione è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="3b927-165">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="3b927-166">Ogni dominio SIP deve disporre di un URL semplice riunione separato, ma sono sufficienti un URL semplice per accesso esterno e un URL semplice di amministrazione per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3b927-166">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="3b927-167">Ogni URL semplice nell'organizzazione deve avere un nome univoco e non può essere un prefisso di un altro URL semplice (ad esempio, non è stato possibile impostare lync.contoso.com/Meet come URL semplice Meet e lync.contoso.com/Meet/Dialin come URL semplice di accesso esterno).</span><span class="sxs-lookup"><span data-stu-id="3b927-167">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="3b927-168">Gli URL semplici non possono contenere il nome di dominio completo di uno dei pool o qualsiasi altra informazione sulla porta https://FQDN:88/meet , ad esempio, non è consentita.</span><span class="sxs-lookup"><span data-stu-id="3b927-168">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="3b927-169">Tutti gli URL semplici devono iniziare con il prefisso https://.</span><span class="sxs-lookup"><span data-stu-id="3b927-169">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="3b927-p112">Gli URL semplici possono includere solo caratteri alfanumerici, ovvero a-z, A-Z, 0-9 e il punto (.). Se si utilizzano altri caratteri, gli URL semplici potrebbero non funzionare come previsto.</span><span class="sxs-lookup"><span data-stu-id="3b927-p112">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.). If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="3b927-172">Modifica degli URL semplici dopo la distribuzione</span><span class="sxs-lookup"><span data-stu-id="3b927-172">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="3b927-173">Se si modifica un URL semplice dopo la distribuzione iniziale, è necessario essere a conoscenza del modo in cui la modifica influisce sui record DNS e sui certificati per gli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="3b927-173">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="3b927-174">Se si modifica la base di un URL semplice, è necessario modificare anche i record DNS e i certificati.</span><span class="sxs-lookup"><span data-stu-id="3b927-174">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="3b927-175">Ad esempio, se si https://lync.contoso.com/Meet cambia https://meet.contoso.com da per cambiare l'URL di base da Lync.contoso.com a meet.contoso.com, è necessario modificare i record DNS e i certificati in modo che facciano riferimento a meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="3b927-175">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="3b927-176">Se l'URL semplice è stato modificato https://lync.contoso.com/Meet da https://lync.contoso.com/Meetingsa, l'url di base di Lync.contoso.com rimane invariato, quindi non sono necessarie modifiche a DNS o certificati.</span><span class="sxs-lookup"><span data-stu-id="3b927-176">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="3b927-177">Ogni volta che si modifica un nome URL semplice, è necessario eseguire **Enable-CsComputer** in ogni Director e front end server per registrare la modifica.</span><span class="sxs-lookup"><span data-stu-id="3b927-177">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3b927-178">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b927-178">See Also</span></span>


[<span data-ttu-id="3b927-179">Requisiti DNS per gli URL semplici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3b927-179">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

