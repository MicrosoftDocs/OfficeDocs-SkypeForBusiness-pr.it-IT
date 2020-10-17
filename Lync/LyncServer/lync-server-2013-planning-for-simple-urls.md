---
title: 'Lync Server 2013: pianificazione per gli URL semplici'
description: 'Lync Server 2013: pianificazione per gli URL semplici.'
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
ms.openlocfilehash: 10a7f2aaf85dafe5facba7cfd2509cfcc8812d67
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558402"
---
# <a name="planning-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="240ec-103">Pianificazione degli URL semplici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="240ec-103">Planning for simple URLs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="240ec-104">_**Ultimo argomento modificato:** 2015-12-11_</span><span class="sxs-lookup"><span data-stu-id="240ec-104">_**Topic Last Modified:** 2015-12-11_</span></span>

<span data-ttu-id="240ec-105">Gli URL semplici agevolano la partecipazione alle riunioni per gli utenti e semplificano gli strumenti di amministrazione di Lync Server per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="240ec-105">Simple URLs make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span>

<span data-ttu-id="240ec-106">Lync Server supporta tre URL semplici:</span><span class="sxs-lookup"><span data-stu-id="240ec-106">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="240ec-107">L'URL **riunione** (meet) viene utilizzato come URL di base per tutte le conferenze nel sito o nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="240ec-107">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="240ec-108">Un esempio di URL semplice Meet è https://meet.contoso.com .</span><span class="sxs-lookup"><span data-stu-id="240ec-108">An example of a Meet simple URL is https://meet.contoso.com.</span></span> <span data-ttu-id="240ec-109">Un URL per una riunione specifica può essere https://meet.contoso.com/ *nomeutente*/7322994.</span><span class="sxs-lookup"><span data-stu-id="240ec-109">A URL for a particular meeting might be https://meet.contoso.com/*username*/7322994.</span></span>
    
    <span data-ttu-id="240ec-110">Con l'URL semplice riunione, i collegamenti per partecipare alle riunioni sono semplici da capire, da comunicare e da distribuire.</span><span class="sxs-lookup"><span data-stu-id="240ec-110">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="240ec-111">L'URL **per accesso esterno** (dialin) consente di accedere alla pagina Web Impostazioni conferenza telefonica con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="240ec-111">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="240ec-112">In questa pagina vengono visualizzati i numeri di accesso esterno alle conferenze con le lingue disponibili, le informazioni di conferenza assegnate (ovvero per le riunioni che non devono essere pianificate) e i controlli DTMF in-Conference, nonché la gestione del PIN (Personal Identification Number) e le informazioni di conferenza assegnate.</span><span class="sxs-lookup"><span data-stu-id="240ec-112">This page displays conference dial-in numbers with their available languages, assigned conference information (that is, for meetings that do not need to be scheduled), and in-conference DTMF controls, and supports management of personal identification number (PIN) and assigned conferencing information.</span></span> <span data-ttu-id="240ec-113">L'URL semplice per accesso esterno è incluso in tutti gli inviti a riunioni, in modo che gli utenti che desiderano eseguire l'accesso esterno alla riunione dispongano delle informazioni necessarie sul numero di telefono e sul PIN.</span><span class="sxs-lookup"><span data-stu-id="240ec-113">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> <span data-ttu-id="240ec-114">Un esempio di URL semplice in accesso esterno è https://dialin.contoso.com .</span><span class="sxs-lookup"><span data-stu-id="240ec-114">An example of the Dial-in simple URL is https://dialin.contoso.com.</span></span>

  - <span data-ttu-id="240ec-115">L' **amministratore** consente di accedere rapidamente al pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="240ec-115">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="240ec-116">Da qualsiasi computer all'interno dei firewall dell'organizzazione, un amministratore può aprire il pannello di controllo di Lync Server digitando l'URL semplice di amministrazione in un browser.</span><span class="sxs-lookup"><span data-stu-id="240ec-116">From any computer within your organization’s firewalls, an admin can open the Lync Server Control Panel by typing the Admin simple URL into a browser.</span></span> <span data-ttu-id="240ec-117">L'URL semplice di amministrazione è interno all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="240ec-117">The Admin simple URL is internal to your organization.</span></span> <span data-ttu-id="240ec-118">Un esempio di URL semplice di amministrazione è https://admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="240ec-118">An example of the Admin simple URL is https://admin.contoso.com</span></span>

<div>

## <a name="simple-url-scope"></a><span data-ttu-id="240ec-119">Ambito degli URL semplici</span><span class="sxs-lookup"><span data-stu-id="240ec-119">Simple URL Scope</span></span>

<span data-ttu-id="240ec-120">È possibile configurare gli URL semplici per un ambito globale oppure specificare URL semplici diversi per ogni sito centrale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="240ec-120">You can configure your simple URLs to have global scope, or you can specify different simple URLs for each central site in your organization.</span></span> <span data-ttu-id="240ec-121">Se sono specificati sia un URL semplice dell'ambito globale che un URL semplice dell'ambito del sito, l'URL semplice dell'ambito del sito ha la precedenza.</span><span class="sxs-lookup"><span data-stu-id="240ec-121">If both a global scope simple URL and a site scope simple URL are specified, the site scope simple URL has precedence.</span></span>

<span data-ttu-id="240ec-p105">Nella maggior parte dei casi, è consigliabile impostare gli URL semplici solo a livello globale, in modo che l'URL semplice riunione di un utente non cambi con lo spostamento da un sito a un altro. L'eccezione è rappresentata da organizzazioni che devono utilizzare numeri di telefono diversi per gli utenti connessi tramite chiamata in ingresso in siti diversi. Si noti che se si imposta in un sito un URL semplice a livello di sito, ad esempio per l'accesso esterno, sarà necessario impostare a livello di sito anche gli altri URL semplici del sito.</span><span class="sxs-lookup"><span data-stu-id="240ec-p105">In most cases, we recommend that you set simple URLs only at the global level, so that a user’s Meet simple URL does not change if they move from one site to another. The exception would be organizations that need to use different telephone numbers for dial-in users at different sites. Note that if you set one simple URL (such as the Dial-in simple URL) at a site to be a site-level simple URL, you must also set the other simple URLs at that site to be site-level as well.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="240ec-125">Se si sceglie di utilizzare gli URL semplici con ambito sito, gli utenti non saranno in grado di spostarsi tra Front-End pool in siti diversi senza che gli utenti ripianificano tutte le riunioni pianificate, in quanto gli URL semplici della riunione sono diversi tra i siti.</span><span class="sxs-lookup"><span data-stu-id="240ec-125">If you choose to use site scoped simple URLs, your users won't be able to move between Front-End pools in different sites without those users rescheduling all of their scheduled meetings as the meeting simple URLs are different between sites.</span></span> <span data-ttu-id="240ec-126">Sono inclusi gli scenari di failover nei quali i pool nelle relazioni di backup si trovano in siti separati.</span><span class="sxs-lookup"><span data-stu-id="240ec-126">This includes fail-over scenarios where pools in backup relationships are in separate sites.</span></span> <span data-ttu-id="240ec-127">Quando è necessario eseguire il failover tra i siti in cui vengono distribuiti gli URL semplici con ambito del sito, gli utenti non saranno in grado di partecipare alle riunioni a causa dell'ambito per l'URL.</span><span class="sxs-lookup"><span data-stu-id="240ec-127">When you need to fail-over between sites where site scoped simple URLs are deployed, users won't be able to join their meetings because of the scope for URL.</span></span> <span data-ttu-id="240ec-128">Per ulteriori informazioni, vedere <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span><span class="sxs-lookup"><span data-stu-id="240ec-128">For further information, check <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsSimpleUrlConfiguration">Get-CsSimpleUrlConfiguration</A>.</span></span>



</div>

<span data-ttu-id="240ec-129">È possibile impostare gli URL semplici globali in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="240ec-129">You can set global simple URLs in Topology Builder.</span></span> <span data-ttu-id="240ec-130">Per impostare un URL semplice a livello di sito, è necessario utilizzare il cmdlet Set-CsSimpleURLConfiguration.</span><span class="sxs-lookup"><span data-stu-id="240ec-130">To set a simple URL at the site level, you must use the Set-CsSimpleURLConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="naming-your-simple-urls"></a><span data-ttu-id="240ec-131">Denominazione degli URL semplici</span><span class="sxs-lookup"><span data-stu-id="240ec-131">Naming Your Simple URLs</span></span>

<span data-ttu-id="240ec-p108">Sono disponibili tre opzioni consigliate per denominare gli URL semplici. L'opzione scelta determina il modo in cui vengono configurati i certificati e i record A DNS che supportano gli URL semplici. In ogni opzione è necessario configurare un URL semplice riunione per ogni dominio SIP dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="240ec-p108">There are three recommended options for naming your simple URLs. Which option you choose has implications for how you set up your DNS A records and certificates which support simple URLs. In each option, you must configure one Meet simple URL for each SIP domain in your organization.</span></span>

<span data-ttu-id="240ec-135">Sono sufficienti sempre nell'intera organizzazione un solo URL semplice per accesso esterno e uno di amministrazione, indipendentemente dal numero di domini SIP presenti.</span><span class="sxs-lookup"><span data-stu-id="240ec-135">You always need just one simple URL in your whole organization for Dial-in, and one for Admin, no matter how many SIP domains you have.</span></span>

<span data-ttu-id="240ec-136">Per informazioni dettagliate sui record e i certificati DNS necessari, vedere [DNS requirements for Simple URLs in Lync server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) e [Certificate Requirements for Internal Servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="240ec-136">For details about the necessary DNS A records and certificates, see [DNS requirements for simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) and [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md) in the Planning documentation.</span></span>

<span data-ttu-id="240ec-137">Nell'opzione 1 viene creato un nuovo nome di dominio SIP per ogni URL semplice.</span><span class="sxs-lookup"><span data-stu-id="240ec-137">In Option 1, you create a new SIP domain name for each simple URL.</span></span>

<span data-ttu-id="240ec-138">Se si utilizza questa opzione, è necessario un record A DNS separato per ogni URL semplice e ogni URL semplice riunione deve essere denominato nei certificati.</span><span class="sxs-lookup"><span data-stu-id="240ec-138">If you use this option, you need a separate DNS A record for each simple URL, and each Meet simple URL must be named in your certificates.</span></span>

### <a name="simple-url-naming-option-1"></a><span data-ttu-id="240ec-139">Opzione 1 di denominazione degli URL semplici</span><span class="sxs-lookup"><span data-stu-id="240ec-139">Simple URL Naming Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="240ec-140"><strong>URL semplice</strong></span><span class="sxs-lookup"><span data-stu-id="240ec-140"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="240ec-141"><strong>Esempio</strong></span><span class="sxs-lookup"><span data-stu-id="240ec-141"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240ec-142">Soddisfare</span><span class="sxs-lookup"><span data-stu-id="240ec-142">Meet</span></span></p></td>
<td><p><span data-ttu-id="240ec-143">https://meet.contoso.comhttps://meet.fabrikam.come così via (uno per ogni dominio SIP dell'organizzazione)</span><span class="sxs-lookup"><span data-stu-id="240ec-143">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240ec-144">Accesso esterno</span><span class="sxs-lookup"><span data-stu-id="240ec-144">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240ec-145">Amministratore</span><span class="sxs-lookup"><span data-stu-id="240ec-145">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="240ec-p109">Con l'opzione 2, gli URL semplici sono basati sul nome di dominio lync.contoso.com. È necessario pertanto un solo record A DNS che consenta tutti e tre i tipi di URL semplici. Questo record A DNS fa riferimento a lync.contoso.com. Sono sempre necessari però record A DNS separati per altri domini SIP dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="240ec-p109">With Option 2, simple URLs are based on the domain name lync.contoso.com. Therefore, you need only one DNS A record which enables all three types of simple URLs. This DNS A record references lync.contoso.com. Additionally, you still need separate DNS A records for other SIP domains in your organization.</span></span>

### <a name="simple-url-naming-option-2"></a><span data-ttu-id="240ec-150">Opzione 2 di denominazione degli URL semplici</span><span class="sxs-lookup"><span data-stu-id="240ec-150">Simple URL Naming Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="240ec-151"><strong>URL semplice</strong></span><span class="sxs-lookup"><span data-stu-id="240ec-151"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="240ec-152"><strong>Esempio</strong></span><span class="sxs-lookup"><span data-stu-id="240ec-152"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240ec-153">Soddisfare</span><span class="sxs-lookup"><span data-stu-id="240ec-153">Meet</span></span></p></td>
<td><p><span data-ttu-id="240ec-154">https://lync.contoso.com/Meethttps://lync.fabrikam.com/Meete così via (uno per ogni dominio SIP dell'organizzazione)</span><span class="sxs-lookup"><span data-stu-id="240ec-154">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240ec-155">Accesso esterno</span><span class="sxs-lookup"><span data-stu-id="240ec-155">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240ec-156">Amministratore</span><span class="sxs-lookup"><span data-stu-id="240ec-156">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="240ec-157">L'opzione 3 è più utile se si dispone di numerosi domini SIP e si desidera che dispongano di URL semplici riunione separati, riducendo però al minimo i requisiti dei certificati e dei record DNS per questi URL semplici.</span><span class="sxs-lookup"><span data-stu-id="240ec-157">Option 3 is most useful if you have many SIP domains, and you want them to have separate Meet simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs.</span></span>

### <a name="simple-url-naming-option-3"></a><span data-ttu-id="240ec-158">Opzione 3 di denominazione degli URL semplici</span><span class="sxs-lookup"><span data-stu-id="240ec-158">Simple URL Naming Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="240ec-159"><strong>URL semplice</strong></span><span class="sxs-lookup"><span data-stu-id="240ec-159"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="240ec-160"><strong>Esempio</strong></span><span class="sxs-lookup"><span data-stu-id="240ec-160"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240ec-161">Soddisfare</span><span class="sxs-lookup"><span data-stu-id="240ec-161">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="240ec-162">Accesso esterno</span><span class="sxs-lookup"><span data-stu-id="240ec-162">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="240ec-163">Amministratore</span><span class="sxs-lookup"><span data-stu-id="240ec-163">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="simple-url-naming-and-validation-rules"></a><span data-ttu-id="240ec-164">Regole di denominazione e convalida degli URL semplici</span><span class="sxs-lookup"><span data-stu-id="240ec-164">Simple URL Naming and Validation Rules</span></span>

<span data-ttu-id="240ec-165">Il generatore di topologie e i cmdlet di Lync Server Management Shell applicano diverse regole di convalida per gli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="240ec-165">Topology Builder and the Lync Server Management Shell cmdlets enforce several validation rules for your simple URLs.</span></span> <span data-ttu-id="240ec-166">È obbligatorio impostare URL semplici riunione e per accesso esterno, mentre l'impostazione dell'URL semplice di amministrazione è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="240ec-166">You are required to set simple URLs for Meet and Dialin, but setting one for Admin is optional.</span></span> <span data-ttu-id="240ec-167">Ogni dominio SIP deve disporre di un URL semplice riunione separato, ma sono sufficienti un URL semplice per accesso esterno e un URL semplice di amministrazione per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="240ec-167">Each SIP domain must have a separate Meet simple URL, but you need only one Dialin simple URL and one Admin simple URL for your whole organization.</span></span>

<span data-ttu-id="240ec-168">Ogni URL semplice nell'organizzazione deve avere un nome univoco e non può essere un prefisso di un altro URL semplice (ad esempio, non è stato possibile impostare lync.contoso.com/Meet come URL semplice Meet e lync.contoso.com/Meet/Dialin come URL semplice di accesso esterno).</span><span class="sxs-lookup"><span data-stu-id="240ec-168">Each simple URL in your organization must have a unique name, and cannot be a prefix of another simple URL (for example, you could not set lync.contoso.com/Meet as your Meet simple URL and lync.contoso.com/Meet/Dialin as your Dialin simple URL).</span></span> <span data-ttu-id="240ec-169">Gli URL semplici non possono contenere il nome di dominio completo di uno dei pool o qualsiasi altra informazione sulla porta, ad esempio, https://FQDN:88/meet non è consentita.</span><span class="sxs-lookup"><span data-stu-id="240ec-169">Simple URL names cannot contain the FQDN of any of your pools, or any port information (for example, https://FQDN:88/meet is not allowed).</span></span> <span data-ttu-id="240ec-170">Tutti gli URL semplici devono iniziare con il prefisso https://.</span><span class="sxs-lookup"><span data-stu-id="240ec-170">All simple URLs must start with the https:// prefix.</span></span>

<span data-ttu-id="240ec-p112">Gli URL semplici possono includere solo caratteri alfanumerici, ovvero a-z, A-Z, 0-9 e il punto (.). Se si utilizzano altri caratteri, gli URL semplici potrebbero non funzionare come previsto.</span><span class="sxs-lookup"><span data-stu-id="240ec-p112">Simple URLs can contain only alphanumeric characters (that is, a-z, A-Z, 0-9, and the period (.). If you use other characters, the simple URLs might not work as expected.</span></span>

</div>

<div>

## <a name="changing-simple-urls-after-deployment"></a><span data-ttu-id="240ec-173">Modifica degli URL semplici dopo la distribuzione</span><span class="sxs-lookup"><span data-stu-id="240ec-173">Changing Simple URLs after Deployment</span></span>

<span data-ttu-id="240ec-174">Se si modifica un URL semplice dopo la distribuzione iniziale, è necessario essere a conoscenza del modo in cui la modifica influisce sui record DNS e sui certificati per gli URL semplici.</span><span class="sxs-lookup"><span data-stu-id="240ec-174">If you change a simple URL after initial deployment, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="240ec-175">Se si modifica la base di un URL semplice, è necessario modificare anche i record DNS e i certificati.</span><span class="sxs-lookup"><span data-stu-id="240ec-175">If the base of a simple URL changes, then you must change the DNS records and certificates as well.</span></span> <span data-ttu-id="240ec-176">Ad esempio, https://lync.contoso.com/Meet se si cambia da per cambiare https://meet.contoso.com l'URL di base da lync.contoso.com a meet.contoso.com, è necessario modificare i record DNS e i certificati in modo che facciano riferimento a meet.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="240ec-176">For example, changing from https://lync.contoso.com/Meet to https://meet.contoso.com changes the base URL from lync.contoso.com to meet.contoso.com, so you would need to change the DNS records and certificates to refer to meet.contoso.com.</span></span> <span data-ttu-id="240ec-177">Se l'URL semplice è stato modificato da https://lync.contoso.com/Meet a https://lync.contoso.com/Meetings , l'URL di base di Lync.contoso.com rimane invariato, quindi non sono necessarie modifiche a DNS o certificati.</span><span class="sxs-lookup"><span data-stu-id="240ec-177">If you changed the simple URL from https://lync.contoso.com/Meet to https://lync.contoso.com/Meetings, the base URL of lync.contoso.com stays the same, so no DNS or certificate changes are needed.</span></span>

<span data-ttu-id="240ec-178">Ogni volta che si modifica un nome URL semplice, è necessario eseguire **Enable-CsComputer** in ogni Director e front end server per registrare la modifica.</span><span class="sxs-lookup"><span data-stu-id="240ec-178">Whenever you change a simple URL name, however, you must run **Enable-CsComputer** on each Director and Front End Server to register the change.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="240ec-179">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="240ec-179">See Also</span></span>


[<span data-ttu-id="240ec-180">Requisiti DNS per gli URL semplici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="240ec-180">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

